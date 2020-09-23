---
title: Déplacer des données de magasin de fichiers vers un nouveau magasin de fichiers dans Skype entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 8/30/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
description: 'Si vous devez supprimer le serveur de fichiers qui fait actuellement Office de magasin de fichiers pour votre déploiement de Skype entreprise Server 2015 ou si vous devez effectuer d’autres modifications qui rendaient le magasin de fichiers actuel indisponible, vous devez d’abord créer un nouveau partage. Ensuite, vous devez effectuer les étapes suivantes :'
ms.openlocfilehash: c9bdc7ac572ecd8a71022e5a267454b795ef7cc6
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215585"
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server-2015"></a>Déplacer des données de magasin de fichiers vers un nouveau magasin de fichiers dans Skype entreprise Server 2015

Si vous devez supprimer le serveur de fichiers qui fait actuellement Office de magasin de fichiers pour votre déploiement de Skype entreprise Server 2015 ou si vous devez effectuer d’autres modifications qui rendaient le magasin de fichiers actuel indisponible, vous devez d’abord créer un nouveau partage. Ensuite, vous devez effectuer les étapes suivantes :

1. Arrêtez les services Skype entreprise Server 2015 qui utilisent le magasin de fichiers que vous envisagez de supprimer.

2. Définissez le magasin de fichiers dans le générateur de topologie et publiez les modifications pour que le nouveau magasin de fichiers soit disponible pour votre déploiement.

3. Déplacez les données vers le nouveau magasin de fichiers.

4. Redémarrez les serveurs ou les services.

5. Si vous le souhaitez, supprimez l’ancien dossier de fichiers et le partage de fichiers.

### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a>Pour déplacer les données du magasin de fichiers vers le nouveau magasin

1. Ouvrez une session sur un ordinateur en tant que membre du groupe Groupe rtcuniversersalserveradmins ou CsServerAdministrator où les outils d’administration de Skype entreprise Server 2015 sont installés.

2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Skype entreprise Server.

3. Dans la barre de navigation de gauche, cliquez sur **Topologie**, puis sur **État**.

4. Pour chaque pool Directeur, directeur, serveur Standard Edition et pool frontal qui utilise le magasin de fichiers que vous envisagez de supprimer, sélectionnez le serveur ou le pool, cliquez sur **action**, puis sur **arrêter tous les services**.

5. Ouvrez une session sur l’ordinateur sur lequel le Générateur de topologies est installé, en tant que membre du groupe Administrateurs du domaine et du groupe RTCUniversalServerAdmins.

6. Démarrez le générateur de topologie : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Skype entreprise Server 2015**, puis sur **Skype entreprise Server 2015Topology Builder**.

7. Sélectionnez un serveur ou un pool qui utilise le magasin de fichiers, puis procédez comme suit :

8. Cliquez avec le bouton droit sur le serveur ou le pool, puis cliquez sur **modifier les propriétés**.

9. Dans **modifier les propriétés**, sous **associations**, sous **magasin de fichiers**, cliquez sur **nouveau**.

10. Dans **définir un nouveau magasin de fichiers**, sous nom de domaine **complet du serveur**de fichiers, tapez le nom de domaine complet (FQDN) du serveur de fichiers. Sous **partage de fichiers**, tapez le nom du dossier pour le nouveau partage de fichiers, puis cliquez sur **OK**.

     > [!IMPORTANT]
     > Cette étape permet de définir un nouveau magasin de fichiers à utiliser dans le générateur de topologie. Vous ne la définissez qu’une seule fois, pas pour chaque serveur. Avant de publier la topologie, vous devez créer le partage de fichiers défini sur le serveur de fichiers défini. Pour plus d’informations, voir [Define the File Store for the Front End](https://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx).

11. Pour chaque serveur ou pool qui utilise le magasin de fichiers, procédez comme suit :

12. Cliquez avec le bouton droit sur le serveur ou le pool, puis cliquez sur **modifier les propriétés**.

13. Dans **modifier les propriétés**, sous **associations**, dans **magasin de fichiers**, sélectionnez le nouveau partage de fichiers, puis cliquez sur **OK**.

14. Publiez la topologie, vérifiez l’état de la réplication, puis exécutez l’Assistant Déploiement de Skype entreprise Server selon vos besoins. Pour plus d’informations, voir [Common Procedures for Removing Lync Servers and Components](https://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).

15. Démarrez une invite de commandes : cliquez sur **Démarrer**, sur **exécuter**, puis tapez cmd.exe.

16. Dans la ligne de commande, tapez le code suivant :

    ```console
    Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>
    ```

    > [!TIP]
    > Le commutateur/S copie sur des fichiers, des répertoires et des sous-répertoires. Le commutateur/XF ignore les fichiers nommés Meeting. active. Les versions actuelles de robocopy.exe avec le commutateur /MT offrent une vitesse de copie bien plus élevée en ayant recours à plusieurs threads. Pour le commutateur/LOG, utilisez un chemin d’accès au répertoire et un nom de fichier journal sous la forme d' C:\Logfiles\log.txt. Ce commutateur crée un fichier journal d’opérations à l’emplacement nommé.

17. Une fois la copie des données terminée, dans le panneau de configuration Lync Server, cliquez sur **topologie**, puis sur **État**.

18. Pour chaque serveur ou pool sur lequel vous avez arrêté les services, sélectionnez le serveur ou le pool, cliquez sur **action**, puis sur **Démarrer tous les services**.

19. Supprimez l’ancien magasin de fichiers de la topologie, puis publiez la topologie. Pour plus d’informations, voir [Remove a file store](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).

20. (Facultatif) Ouvrez une session sur l’ordinateur qui contient le magasin de fichiers que vous venez de supprimer en tant que membre du groupe Administrateurs local ou du groupe Administrateurs de domaine, puis supprimez l’ancien répertoire et l’ancien partage de fichiers.

## <a name="see-also"></a>Voir aussi

[Réattribuer un serveur à un magasin de fichiers différent](https://technet.microsoft.com/library/18509cce-a4d2-4537-a822-f99de6d7598e.aspx)

[Supprimer un magasin de fichiers](https://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)
