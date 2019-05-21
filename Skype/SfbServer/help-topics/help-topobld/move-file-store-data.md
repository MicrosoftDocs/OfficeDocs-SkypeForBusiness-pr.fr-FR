---
title: Déplacer des données de magasin de fichiers vers un nouveau magasin de fichiers dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 8/30/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
description: 'Si vous avez besoin de supprimer le serveur de fichiers qui sert de magasin de fichiers pour votre déploiement de Skype entreprise Server 2015 ou si vous avez besoin d’apporter d’autres modifications pour rendre le stockage de fichiers actuel indisponible, vous devez tout d’abord créer un nouveau partage. Ensuite, procédez comme suit :'
ms.openlocfilehash: c2d447734d05b03b54a27640be872d360658636d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34285616"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server-2015"></a>Move File Store Data to a New File Store in Skype for Business Server 2015

Si vous avez besoin de supprimer le serveur de fichiers qui sert de magasin de fichiers pour votre déploiement de Skype entreprise Server 2015 ou si vous avez besoin d’apporter d’autres modifications pour rendre le stockage de fichiers actuel indisponible, vous devez tout d’abord créer un nouveau partage. Ensuite, procédez comme suit :

1. Fermez les services Skype entreprise Server 2015 qui utilisent le magasin de fichiers que vous envisagez de supprimer.

2. Définissez le magasin de fichiers dans le générateur de topologie et publiez les modifications pour rendre le nouveau magasin de fichiers disponible pour votre déploiement.

3. Déplacez les données vers le nouveau magasin de fichiers.

4. Redémarrez les serveurs ou services.

5. Vous pouvez également supprimer les partages de fichiers et dossier de fichiers anciens.

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a>Pour déplacer les données du magasin de fichiers d’un magasin de fichiers vers un autre

1. Connectez-vous à un ordinateur en tant que membre du groupe RTCUniversersalServerAdmins ou CsServerAdministrator dans lequel Skype entreprise Server 2015, outils d’administration sont installés.

2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.

3. Dans la barre de navigation de gauche, cliquez sur **Topologie**, puis sur **État**. 

4. Pour chaque pool de réalisateurs, directeur, serveur Standard Edition et pool frontal qui utilise le magasin de fichiers que vous envisagez de supprimer, sélectionnez le serveur ou le pool, cliquez sur **action**, puis cliquez sur **arrêter tous les services**.

5. Ouvrez une session sur l’ordinateur sur lequel le générateur de topologie est installé en tant que membre du groupe administrateurs de domaine et du groupe RTCUniversalServerAdmins.

6. Démarrer le générateur de topologie: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Skype entreprise Server 2015**, puis sur **Skype entreprise Server 2015Topology Builder**.

7. Sélectionnez un serveur ou un pool qui utilise le magasin de fichiers et procédez comme suit :

8. Cliquez avec le bouton droit sur le serveur ou le pool, puis cliquez sur **Modifier les propriétés**. 

9. Dans **Modifier les propriétés**, sous **Associations**, puis sous **Magasin de fichiers**, cliquez sur **Nouveau**.

10. Dans **Définir un nouveau magasin de fichiers**, sous **Nom de domaine complet du serveur de fichiers**, saisissez le nom de domaine complet du serveur de fichiers. Sous **Partage de fichiers**, saisissez le nom de dossier pour le nouveau partage de fichiers et cliquez sur **OK**.

     > [!IMPORTANT]
     > Cette étape définit un nouveau magasin de fichiers à utiliser dans le générateur de topologie. Définissez-le une seule fois, non pour chaque serveur. Avant de publier la topologie, vous devez créer le partage de fichiers sur le serveur de fichiers défini. Pour plus d’informations, reportez-vous à la section [Define the File Store for the Front End](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx).

11. Pour chaque serveur ou pool qui utilise le magasin de fichiers, procédez comme suit :

12. Cliquez avec le bouton droit sur le serveur ou le pool, puis cliquez sur **Modifier les propriétés**.

13. Dans **Modifier les propriétés**, sous **Associations**, dans **Magasin de fichiers**, sélectionnez le nouveau partage de fichiers, puis cliquez sur **OK**.

14. Publiez la topologie, vérifiez l’état de la connexion, puis exécutez l’Assistant Déploiement de Skype entreprise Server selon vos besoins. Pour plus d’informations, reportez-vous à la section [Common Procedures for Removing Lync Servers and Components](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).

15. Démarrez une invite de commandes: cliquez sur **Démarrer**, sur **exécuter**, puis tapez cmd. exe.

16. Dans la ligne de commande, tapez ce qui suit :

    ```
    Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>
    ```

    > [!TIP]
    > Le commutateur /S permet de copier sur des fichiers, des répertoires et des sous-répertoires. Le commutateur /XF permet d’ignorer des fichiers nommés Meeting.Active. Les versions actuelles du fichier robocopy.exe avec le commutateur /MT augmentent considérablement la vitesse de copie à l’aide de plusieurs threads. Pour le commutateur/LOG, utilisez un chemin d’accès au répertoire et un nom de fichier journal sous la forme de C:\Logfiles\log.txt. Ce commutateur crée un fichier journal d’opérations à l’emplacement nommé.

17. Lorsque la copie des données est terminée, dans le panneau de configuration de Lync Server, cliquez sur **Topology**, puis sur **Status**.

18. Pour chaque serveur et pool sur lesquels vous avez arrêté les services, sélectionnez le serveur ou pool, cliquez sur **Action**, puis sur **Démarrer tous les services**.         

19. Supprimez l’ancien magasin de fichiers de la topologie et publiez la topologie. Pour plus d’informations, reportez-vous à la section [Remove a file store](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).

20. (Facultatif) Connectez-vous à l’ordinateur qui contient le magasin de fichiers que vous venez de supprimer en tant que membre du groupe Administrateurs local ou du groupe Administrateurs de domaines et supprimez le partage de fichiers et le répertoire anciens.

## <a name="see-also"></a>Voir aussi

[Réattribuer un serveur à un autre magasin de fichiers](https://technet.microsoft.com/library/18509cce-a4d2-4537-a822-f99de6d7598e.aspx)

[Supprimer un magasin de fichiers](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)
