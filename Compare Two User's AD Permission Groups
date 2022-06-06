
$ID1 = Read-Host -Prompt 'Enter the first user account that you would like to compare'
    $ID2 = Read-Host -Prompt 'Enter the second user account that you would like to compare'

    $user1 = (Get-ADPrincipalGroupMembership -Identity $ID1 | Select-Object Name | Sort-Object -Property Name).Name
    Write-Verbose ($user1 -join "; ")
    $user2 = (Get-ADPrincipalGroupMembership -Identity $ID2 | Select-Object Name | Sort-Object -Property Name).Name
    Write-Verbose ""
    Write-Verbose ($user2 -join "; ")
    $SameGroups = (Compare-Object $user1 $user2 -PassThru -IncludeEqual -ExcludeDifferent)
    Write-Verbose ""
    Write-Verbose ($SameGroups -join "; ")
    $UniqueID1 = (Compare-Object $user1 $user2 -PassThru | Where-Object {$_.SideIndicator -eq "<="})
    Write-Verbose ""
    Write-Verbose ($UniqueID1 -join "; ")
    $UniqueID2 = (Compare-Object $user1 $user2 -PassThru | Where-Object {$_.SideIndicator -eq "=>"})
    Write-Verbose ""
    Write-Verbose ($UniqueID2 -join "; ")
    $ID1Name = (Get-ADUser -Identity $ID1 | Select-Object Name).Name
    Write-Verbose ""
    Write-Verbose ($ID1Name -join "; ")
    $ID2Name = (Get-ADUser -Identity $ID2 | Select-Object Name).Name
    Write-Verbose ""
    Write-Verbose ($ID2Name -join "; ")

    Write-Host "--------------------------------------------------------------------------"
    Write-Host "[$ID1Name] and [$ID2Name] have the following groups in common:"
    Write-Host "--------------------------------------------------------------------------"
    $SameGroups
    Write-Host ""
    Write-Host "--------------------------------------------------------------------------"
    Write-Host "The following groups are unique to [$ID1Name]:"
    Write-Host "--------------------------------------------------------------------------"
    $UniqueID1
    Write-Host ""
    Write-Host "--------------------------------------------------------------------------"
    Write-Host "The following groups are unique to [$ID2Name]:"
    Write-Host "--------------------------------------------------------------------------"
    $UniqueID2
    Write-Host ""
    
    Read-Host -Prompt "Press Enter to exit"
