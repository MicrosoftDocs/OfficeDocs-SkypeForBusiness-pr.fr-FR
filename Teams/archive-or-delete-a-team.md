---
title: Archiver ou supprimer une équipe dans Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: jastark
search.appverid: MET150
description: Dans cet article, vous allez découvrir comment archiver ou supprimer définitivement une équipe dans Microsoft Teams.
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c310794d439af79e53618d9b6e93e567c652cf47
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2022
ms.locfileid: "61766637"
---
# <a name="archive-or-delete-a-team-in-microsoft-teams"></a>Archiver ou supprimer une équipe dans Microsoft Teams

Au fil du temps, une équipe créée dans Microsoft Teams risque de ne plus être utilisée ou vous pouvez souhaiter d’archiver ou de supprimer une équipe à la fin d’un projet. Si vous êtes un administrateur Microsoft Teams, suivez les étapes décrites dans cet article pour archiver ou supprimer une équipe qui n’est plus nécessaire.

Lorsque vous archivez une équipe, toute l’activité de cette équipe cesse. L’archivage d’une équipe archive également les canaux privés au sein de l’équipe et les collections de sites associées.  Cependant, vous pouvez toujours ajouter ou supprimer des membres et mettre à jour les rôles et vous pouvez toujours afficher toutes les activités de l'équipe dans les canaux, fichiers et conversations instantanées standard et privés.

Lorsque vous supprimez une équipe, l’activité d’une équipe dans les canaux standard et privés (et les collections de sites associées), les fichiers et les conversations sont également supprimés.

> [!IMPORTANT]
> Les équipes archivées peuvent être réactivées, mais vous ne pouvez pas restaurer directement une équipe qui a été supprimée. Vous devez commencer par archiver l’équipe et retarder la suppression jusqu’à ce que vous soyez certain que vous n’avez plus besoin de l’équipe.

## <a name="archive-a-team"></a>Archiver une équipe

Suivez ces étapes pour archiver une équipe. Vous devez être un administrateur du service Teams pour apporter ces modifications. Voir [Gérer Teams grâce aux rôles d’administrateur Teams](./using-admin-roles.md) afin d’en savoir plus sur l’obtention de rôles et d’autorisations d’administrateur.

1. Dans le Centre d’administration, **sélectionnez Teams.**
2. Sélectionnez une équipe en cliquant sur le nom de l’équipe.
3. Sélectionnez **Archiver**. Le message suivant s’affichera.

    ![Capture d’écran Teams message d’archivage.](media/teams-archive-message.png)

4. Pour empêcher les utilisateurs de modifier le contenu du site SharePoint et de l’onglet Wiki associés à l’équipe, sélectionnez Rendre le site SharePoint en lecture seule pour les membres de **l’équipe.** (Teams propriétaires pourront toujours modifier ce contenu.)
5. Sélectionnez **Archiver** pour archiver l’équipe. Le statut de l’équipe est alors archivé.  Il est déplacé vers l’intérieur des équipes masquées situées en bas de la liste d’équipes, et une petite icône représentant l’état archivé est ajoutée à côté. 

## <a name="make-an-archived-team-active"></a>Rendre une équipe archivée active

Pour réactiver une équipe archivée, procédez comme suit.

1. Dans le Centre d’administration, **sélectionnez Teams.**
2. Sélectionnez une équipe en cliquant sur le nom de l’équipe.
3. Sélectionnez **Restaurer.** Le statut de l’équipe passera à **Active**. Notez qu’il ne sera pas automatiquement déplacé vers **vos équipes.**

## <a name="delete-a-team"></a>Supprimer une équipe

Si l’équipe ne sera pas nécessaire, vous pouvez la supprimer plutôt que de l’archiver. Pour supprimer une équipe, suivez ces étapes.

1.  Dans le Centre d’administration, **sélectionnez Teams.**
2.  Sélectionnez une équipe en cliquant sur le nom de l’équipe.
3.  Sélectionnez **Supprimer**. Un message de confirmation s’affichera.
4.  Sélectionnez **Supprimer** pour supprimer définitivement l’équipe.

## <a name="restore-a-deleted-team"></a>Restaurer une équipe supprimée

Pour restaurer une équipe supprimée, suivez ces étapes en restaurant Microsoft 365 groupe associé à l’équipe. La restauration du Microsoft 365 d’une équipe restaure le contenu de l’équipe, y compris les onglets, les canaux standard et les canaux privés et les collections de sites associées.

Par défaut, un groupe de Microsoft 365 supprimé est conservé pendant 30 jours. Cette période de 30 jours est appelée « suppression réversible », car vous avez la possibilité de le restaurer. Pour en savoir plus, voir [Restaurer un groupe supprimé.](/microsoft-365/admin/create-groups/restore-deleted-group)

### <a name="install-the-azureadpreview-module"></a>Installez le module AzureADPreview

1. Ouvrez Windows PowerShell en tant qu’administrateur.
2. Si une version antérieure du module AzureADPreview est installée ou si le module AzureAD est installé, désinstallez-le en exécutant l’une des opérations suivantes :

    ```PowerShell
    Uninstall-Module AzureADPreview
    ```

    ```PowerShell
    Uninstall-Module AzureAD
    ```
3. Installez la dernière version du module AzureADPreview en exécutant la commande suivante :

    ```PowerShell
    Install-Module AzureADPreview
    ```

### <a name="restore-the-deleted-microsoft-365-group"></a>Restaurer le groupe de Microsoft 365 supprimé

1. Connectez-vous à Azure AD en exécutant la commande suivante :
    ```PowerShell
    Connect-AzureAD
    ```
    Lorsque vous y êtes invité, connectez-vous à l’aide de votre compte d’administrateur et de votre mot de passe.  
2. Exécutez la liste suivante pour afficher la liste de tous les groupes de rétention supprimés de Microsoft 365 supprimés de nouveau pour une période de 30 jours. Utilisez le **paramètre -All $True** si vous avez de nombreux groupes.
    ```PowerShell
    Get-AzureADMSDeletedGroup
    ```
3. Recherchez le groupe à restaurer, puis notez le `Id` .
4. Exécutez l’ordre suivant pour restaurer le groupe, où se trouve `[Id]` l’ID de groupe.
    ```PowerShell
    Restore-AzureADMSDeletedDirectoryObject -Id [Id]
    ```
5.  Exécutez l’information suivante pour vérifier que le groupe a été correctement restauré, à l’endroit où se trouve `[Id]` l’ID de groupe.
    ```PowerShell
    Get-AzureADGroup -ObjectId [Id]
    ```

    L’exécution du processus de restauration peut prendre jusqu’à 24 heures, après quoi l’équipe et le contenu associé à l’équipe, y compris les onglets et les canaux, s’affichent dans Teams.
    
## <a name="related-topics"></a>Sujets associés

- [Archiver ou restaurer une équipe](https://support.microsoft.com/office/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7) 
