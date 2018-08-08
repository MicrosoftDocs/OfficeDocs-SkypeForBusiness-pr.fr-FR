---
title: Exemple de script PowerShell - Créer une équipe à l’échelle de l’entreprise dans Microsoft Teams
author: ninadara
ms.author: ninadara
manager: serdars
ms.date: 02/07/2018
ms.topic: article
ms.service: msteams
description: Utilisez ce script PowerShell pour créer une équipe publique à l’échelle de l’entreprise dans Teams.
localization_priority: Priority
MS.collection: Strat_MT_TeamsAdmin
ms.openlocfilehash: 26933c97aaa5d16c28a771e3d45c31174b807c07
ms.sourcegitcommit: 0c2d1766b96b99d9985f5a0f4f90b8d8bd9aa3ef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/08/2018
ms.locfileid: "18999158"
---
<a name="powershell-script-sample---create-a-company-wide-team-in-microsoft-teams"></a>Exemple de script PowerShell - Créer une équipe à l’échelle de l’entreprise dans Microsoft Teams
-------------------------------------------------------------------------

Ce script PowerShell crée une équipe publique à l’échelle de l’entreprise dans Teams. Ce script utilise le module PowerShell MicrosoftTeams (actuellement en version bêta) pour créer une équipe publique à l’échelle de l’entreprise. Il utilise également le module PowerShell AzureAD pour récupérer la liste des utilisateurs de votre client. 

Pour obtenir des instructions détaillées sur l’utilisation de ce script PowerShell, consultez notre didacticiel, [Créer une équipe à l’échelle de l’entreprise dans Teams avec PowerShell](../Company-wide-team-creation-powershell.yml).

Si vous débutez avec PowerShell et avez besoin d’aide pour démarrer, reportez-vous à la rubrique [Présentation d’Azure PowerShell](https://docs.microsoft.com/powershell/azure/overview?view=azurermps-5.1.1).


## <a name="sample-script"></a>Exemple de script

> [!TIP]
> Un fichier de script PowerShell est un fichier texte avec l’extension .PS1. Pour utiliser ce script, cliquez sur **Copier** et collez le code dans un fichier texte. Enregistrez-le avec le nom de fichier CreateCompanyWideTeam.ps1, et vous avez un script PowerShell.

````powershell
<#
.SYNOPSIS
This script allows you to create a company-wide team.
.DESCRIPTION
Use this script with the MicrosoftTeams PowerShell version 0.9.0 beta module to create a team with members and channels that you specify. Also leverages the AzureAD module to find all members to add.
.PARAMETER Owners
The comma-separated list of owners for your Team, who handle team settings and membership management. The owners should be specified by their User Principal Name. You must specify a minimum of two owners.
.PARAMETER TeamName
The name of your company-wide team. For example, this could be your company name.
.PARAMETER TeamDescription
The description of your company-wide team, in quotes.
.PARAMETER Channels
The comma-separated list of names of all the initial channels you want to set up. For example: "Announcements","Social at Work","Teamwork at Contoso".
.PARAMETER GroupID
If you have already created the group for your company-wide team, specify its GroupID. You can get this value from the display of the “Get-AzureADGroup | Sort DisplayName | Select DisplayName,ObjectID” command. This script had an issue during the rest of the execution and stopped early. 
.PARAMETER Members
The comma-separated list of members for your team that you want to manually add. To use this script a minimum of two members must be added. The members should be specified by their User Principal Name. To manually just add a single member, use the “Add-TeamUser -GroupId $IdOfGroup -Role Member -User $member” command.
#>
param(
    [Parameter(Mandatory=$false)][System.Collections.ArrayList]$Owners,
    [Parameter(Mandatory=$false)][System.String]$TeamName,
    [Parameter(Mandatory=$false)][System.String]$TeamDescription,
    [Parameter(Mandatory=$false)][System.Collections.ArrayList]$Channels,
    [Parameter(Mandatory=$false)][System.String]$GroupID,
    [Parameter(Mandatory=$false)][System.Collections.ArrayList]$Members
)

function Create-Team(){
    Write-Host("Starting Team Creation")
    $GroupID = (New-Team -DisplayName $TeamName -AccessType Public -Description $TeamDescription).GroupId

    if([string]::IsNullOrEmpty($GroupID)){
        Write-Host("Team creation failed, please investigate and try again")
        Return
    }

    Write-Host("Team GroupID:", $GroupID)

    return ,$GroupID
} 

 
function Add-Channels($IdOfGroup){
        Write-Host("Starting Channel addition")
    foreach($channel in $Channels)
        {
            Write-Host("Enter Channel Description for " + $channel + " channel")
            $channelDescription = Read-Host
            New-TeamChannel -GroupId $IdOfGroup -DisplayName $channel -Description $channelDescription
        }
}
 
 
function Add-Members ($IdOfGroup){
    Write-Host("Starting Member addition")
    $allUsersInTenant = $Members 

    ## Only fetch full user list, if one isn't supplied
    if([string]::IsNullOrEmpty($Members))
    {
        $Error.Clear()
 

        Write-Host("Starting connection to AzureAD module") 
        Connect-AzureAD
 
        if($Error){
            Write-Host("Unable to connect to AzureAD. Please investigate and try again. To install the commandlet, use this command: Install-Module AzureAD")
            Return
        }
    
        

       ## Fetch all the users and create the member list
        $allUsersInTenant = (Get-AzureADUser).UserPrincipalName 

 
        Disconnect-AzureAD
    } 
    
    $NotAddedMembers = [System.Collections.ArrayList]@()
    $existingTeamMembers = (Get-TeamUser -GroupId $IdOfGroup).User

    foreach($user in $allUsersInTenant){
        $Error.Clear()

        if(!$existingTeamMembers.Contains($user)){
            Write-Host($user)

            if($Owners.Contains($user)){
                Add-TeamUser -GroupId $IdOfGroup -Role Owner -User $user.ToString()
                
                if($Error){
                    $NotAddedMembers.Add([Tuple]::Create($user,"Owner"))
                }
            }
            else{
                Add-TeamUser -GroupId $IdOfGroup -Role Member -User $user.ToString()
                
                if($Error) {
                    $NotAddedMembers.Add([Tuple]::Create($user,"Member"))
                }
            }
        }
    } 

    if($NotAddedMembers.Count > 0) {
        Write-Host("There are some members that did not get added, please retry these specific users")
        Write-Host($NotAddedMembers)
    } 


    ##Clear member addition errors
    $Error.Clear()
}
 
 
 
 
##Main Script
$Error.Clear()
Write-Host("Starting connection to MicrosoftTeams module") 

Connect-MicrosoftTeams
 
if($Error){
    Write-Host("There was an error installing\connecting to the Microsoft Teams PowerShell module. Please investigate. To install the module use the follow command: Install-Module MicrosoftTeams ")
    Return
}

##Create the team if existing GroupID isn't supplied. It's possible a Tenant Wide team was created, but there was an error adding members.
if([string]::IsNullOrEmpty($GroupID)){

    if([string]::IsNullOrEmpty($TeamName)){
        Write-Host("Missing an argument for parameter 'TeamName' and 'GroupID'. Specify a parameter of type 'System.String' and try again for either GroupID or TeamName and TeamDescription")
        Return
    }
    $GroupID = Create-Team
} 
 
if($Channels.Count -gt 0){
    Add-Channels $GroupID
} 

Add-Members $GroupID 
 
Disconnect-MicrosoftTeams

````


## <a name="script-explanation"></a>Explication du script


Pour obtenir des instructions détaillées sur l’utilisation de ce script PowerShell, consultez notre didacticiel, [Créer une équipe à l’échelle de l’entreprise dans Teams avec PowerShell](../Company-wide-team-creation-powershell.yml)

Ce script comporte 5 sections (répertoriées dans l’ordre, de haut en bas) :
1. **Documentation et définitions des variables**
2. **Fonction Create-Team** : crée une équipe si nécessaire. Si vous ne spécifiez pas d’ID de groupe, cette section créera l’équipe avec le nom et le description spécifiés.
3. **Fonction Add-Channels** : si vous avez spécifié des canaux, c’est ici que la description est demandée et que le canal est ensuite créé. 
4. **Fonction Add-Members** : effectue toute la gestion des membres. Cette section se connecte à AzureAD, récupère un ensemble d’utilisateurs puis les ajoute à l’équipe si vous ne fournissez de liste des membres. Elle gère la logique d’ajout des propriétaires et des membres, et n’ajoute pas les membres qui font déjà partie de l’équipe. 
5. **Main program** : ordre dans lequel les fonctions sont exécutées. 


