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
description: Dans cet article, vous allez découvrir comment archiver ou supprimer définitivement une équipe dans Microsoft Teams.
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e17f27cdbaaca9070d87714b58906df96539e12e
ms.sourcegitcommit: 3e5cac88911611c94c0330bf50af9c34db308cdf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/22/2020
ms.locfileid: "45372193"
---
<a name="archive-or-delete-a-team-in-microsoft-teams"></a>Archiver ou supprimer une équipe dans Microsoft Teams
===========================================

Au fil du temps, une équipe créée dans Microsoft Teams risque de ne plus être utilisée ou vous pouvez souhaiter d’archiver ou de supprimer une équipe à la fin d’un projet. Si vous êtes un administrateur Microsoft Teams, suivez les étapes décrites dans cet article pour archiver ou supprimer une équipe qui n’est plus nécessaire.

Lorsque vous archivez une équipe, toute l’activité de cette équipe cesse. L’archivage d’une équipe archive également les canaux privés au sein de l’équipe et les collections de sites associées.  Cependant, vous pouvez toujours ajouter ou supprimer des membres et mettre à jour les rôles et vous pouvez toujours afficher toutes les activités de l'équipe dans les canaux, fichiers et conversations instantanées standard et privés.

Lorsque vous supprimez une équipe, l’activité d’équipe dans les canaux standard et privés (et les collections de sites associées), les fichiers et les conversations instantanées est également supprimée.

> [!IMPORTANT]
> Les équipes archivées peuvent être réactivées, mais vous ne pouvez pas restaurer directement une équipe qui a été supprimée. Vous devez commencer par archiver l’équipe et retarder la suppression jusqu’à ce que vous soyez certain que vous n’avez plus besoin de l’équipe.

## <a name="archive-a-team"></a>Archiver une équipe

Suivez ces étapes pour archiver une équipe. Pour effectuer ces modifications, vous devez être un administrateur de service Teams. Pour plus d’informations sur l’accès aux rôles d’administrateur et aux autorisations, voir [utiliser les rôles d’administrateur d’équipes pour gérer teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) .

1. Dans le centre d’administration, sélectionnez **teams**.
2. Sélectionnez une équipe en cliquant sur le nom de l’équipe.
3. Sélectionnez **Archiver**. Le message suivant s’affichera.

    ![Capture d’écran du message archive d’équipe](media/teams-archive-message.png)

4. Pour empêcher d’autres personnes de modifier le contenu du site SharePoint et de l’onglet wiki associé à l’équipe, sélectionnez **définir le site SharePoint en lecture seule pour les membres de l’équipe**. Les propriétaires d’équipes pourront toujours modifier ce contenu.
5. Sélectionnez **Archiver** pour archiver l’équipe. Le statut de l’équipe passera à **Archivé**.

## <a name="make-an-archived-team-active"></a>Rendre une équipe archivée active

Pour réactiver une équipe archivée, procédez comme suit.

1. Dans le centre d’administration, sélectionnez **teams**.
2. Sélectionnez une équipe en cliquant sur le nom de l’équipe.
3. Sélectionnez **Désarchiver**. Le statut de l’équipe passera à **Active**.

## <a name="delete-a-team"></a>Supprimer une équipe

Si l’équipe ne sera pas nécessaire, vous pouvez la supprimer plutôt que de l’archiver. Pour supprimer une équipe, suivez ces étapes.

1.  Dans le centre d’administration, sélectionnez **teams**.
2.  Sélectionnez une équipe en cliquant sur le nom de l’équipe.
3.  Sélectionnez **Supprimer**. Un message de confirmation s’affichera.
4.  Sélectionnez **Supprimer** pour supprimer définitivement l’équipe.

## <a name="restore-a-deleted-team"></a>Restaurer une équipe supprimée

Pour restaurer une équipe supprimée en restaurant le groupe Microsoft 365 associé à l’équipe, procédez comme suit. La restauration du groupe Microsoft 365 pour une équipe restaure le contenu de l’équipe, y compris les onglets, les canaux standard, les canaux privés et les collections de sites associées.

Par défaut, un groupe Microsoft 365 supprimé est conservé pendant 30 jours. Cette période de 30 jours est appelée « suppression réversible », car vous avez la possibilité de le restaurer. Pour en savoir plus, voir [restaurer un groupe supprimé](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group).

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

### <a name="restore-the-deleted-microsoft-365-group"></a>Restaurer le groupe Microsoft 365 supprimé

1. Connectez-vous à Azure AD en exécutant la commande suivante :
    ```PowerShell
    Connect-AzureAD
    ```
    Lorsque vous y êtes invité, connectez-vous à l’aide de votre compte d’administrateur et de votre mot de passe.  
2. Exécutez la commande suivante pour afficher la liste de tous les groupes Microsoft 365 supprimés par logiciel qui sont toujours dans la période de rétention de 30 jours. Utilisez le paramètre **-All $True** si vous avez un grand nombre de groupes.
    ```PowerShell
    Get-AzureADMSDeletedGroup
    ```
3. Trouvez le groupe que vous voulez restaurer, puis notez l’ID.
4. Exécutez la commande suivante pour restaurer le groupe, où [id] est l’ID de groupe.
    ```PowerShell
    Restore-AzureADMSDeletedDirectoryObject -Id [Id]
    ```
5.  Exécutez la commande suivante pour vérifier que le groupe a été correctement restauré, où [id] est l’ID de groupe.
    ```PowerShell
    Get-AzureADGroup -ObjectId [Id]
    ```

    L’exécution du processus de restauration peut prendre jusqu’à 24 heures, après quoi l’équipe et le contenu associé à l’équipe, y compris les onglets et les canaux, s’affichent dans Teams.
