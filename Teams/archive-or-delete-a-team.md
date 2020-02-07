---
title: Archiver ou supprimer une équipe dans Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: jastark
search.appverid: MET150
description: Découvrez comment archiver ou supprimer définitivement une équipe.
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e367fe85f1af35391fa00b4a416b6e796383d962
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41826402"
---
<a name="archive-or-delete-a-team-in-microsoft-teams"></a>Archiver ou supprimer une équipe dans Microsoft Teams
===========================================

Au fil du temps, une équipe créée dans Microsoft teams peut ne pas être utilisée ou vous voudrez peut-être archiver ou supprimer une équipe à la fin d’un projet. Si vous êtes un administrateur de Microsoft Teams, suivez les étapes décrites dans cet article pour archiver ou supprimer une équipe qui n’est plus nécessaire.

Lorsque vous archivez une équipe, toutes les activités pour cette équipe cessent. L’archivage d’une équipe Archive également les canaux privés de l’équipe et les collections de sites qui lui sont associées.  Toutefois, vous pouvez toujours ajouter ou supprimer des membres et mettre à jour les rôles, et vous pouvez toujours afficher toutes les activités de l’équipe dans les canaux, fichiers et discussions standard et privés.

Lorsque vous supprimez une équipe, l’activité d’une équipe dans des canaux standard et privés (et collections de sites associées), des fichiers et des discussions est également supprimée.

> [!IMPORTANT]
> Les équipes archivées peuvent être réactivées, mais vous ne pouvez pas restaurer directement une équipe qui a été supprimée. Envisagez d’archiver d’abord l’équipe et de différer la suppression jusqu’à ce que vous soyez sûr que vous n’avez plus besoin de l’équipe.

## <a name="archive-a-team"></a>Archiver une équipe

Pour archiver une équipe, procédez comme suit.

1. Dans le centre d’administration de Microsoft Teams, sélectionnez **teams**.
2. Pour sélectionner une équipe, cliquez sur son nom.
3. Sélectionnez **Archive**. Le message suivant s’affiche.

    ![Capture d’écran du message Archive teams](media/teams-archive-message.png)

4. Si vous voulez que le site SharePoint de l’équipe soit en lecture seule, activez la case à cocher.
5. Sélectionnez **Archive** pour archiver l’équipe. Le statut de l’équipe devient **Archivé**.

## <a name="make-an-archived-team-active"></a>Rendre une équipe archivée active

Procédez comme suit pour rendre une équipe archivée active de nouveau.

1. Dans le centre d’administration de Microsoft Teams, sélectionnez **teams**.
2. Pour sélectionner une équipe, cliquez sur son nom.
3. Sélectionnez ne pas **Archiver**. Le statut de l’équipe devient **actif**.

## <a name="delete-a-team"></a>Supprimer une équipe

Si l’équipe ne sera pas tenue à l’avenir, vous pouvez la supprimer au lieu d’archiver celle-ci. Pour supprimer une équipe, procédez comme suit.

1.  Dans le centre d’administration de Microsoft Teams, sélectionnez **teams**.
2.  Pour sélectionner une équipe, cliquez sur son nom.
3.  Sélectionnez **supprimer**. Un message de confirmation s’affiche.
4.  Sélectionnez **supprimer** pour supprimer définitivement l’équipe.

## <a name="restore-a-deleted-team"></a>Restaurer une équipe supprimée

Pour restaurer une équipe supprimée en restaurant le groupe Office 365 associé à l’équipe, procédez comme suit. Restauration du groupe Office 365 pour une équipe, restaure le contenu de l’équipe, y compris les onglets, les canaux standard et les canaux privés et les collections de sites associées.

Par défaut, un groupe Office 365 supprimé est conservé pendant 30 jours. Ce délai de 30 jours est appelé « suppression conditionnelle », car vous pouvez restaurer le groupe. Pour en savoir plus, voir [restaurer un groupe Office 365 supprimé](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group).

### <a name="install-the-azureadpreview-module"></a>Installer le module AzureADPreview

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

### <a name="restore-the-deleted-office-365-group"></a>Restaurer le groupe Office 365 supprimé

1. Connectez-vous à Azure AD en exécutant la commande suivante :
    ```PowerShell
    Connect-AzureAD
    ```
    Lorsque vous y êtes invité, connectez-vous à l’aide de votre compte d’administrateur et de votre mot de passe.  
2. Exécutez la commande suivante pour afficher la liste de tous les groupes Office 365 supprimés par logiciel qui sont toujours dans la période de rétention de 30 jours. Utilisez le paramètre **-All $True** si vous avez de nombreux groupes.
    ```PowerShell
    Get-AzureADMSDeletedGroup
    ``` 
3. Recherchez le groupe que vous voulez restaurer, puis notez son ID.
4. Exécutez la commande suivante pour restaurer le groupe, où [id] est l’ID du groupe.
    ```PowerShell
    Restore-AzureADMSDeletedDirectoryObject -Id [Id]
    ```
5.  Exécutez la commande suivante pour vérifier que le groupe a été correctement restauré, où [id] est l’ID du groupe.
    ```PowerShell
    Get-AzureADGroup -ObjectId [Id]
    ```

    Le processus de restauration peut s’écouler jusqu’à 24 heures, après lequel l’équipe et le contenu associés à l’équipe, y compris les onglets et les canaux, s’affichent dans Teams.
