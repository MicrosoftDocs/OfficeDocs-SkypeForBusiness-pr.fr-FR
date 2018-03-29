---
title: Déplacer des données de magasin de fichiers vers un nouveau magasin de fichiers dans Skype Entreprise Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/30/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8d1d5819-add2-4f5d-a436-74c00a281df0
description: 'Si vous devez supprimer le serveur de fichiers qui sert actuellement le stockage de fichiers de votre Skype pour le déploiement de Business Server 2015, ou si vous devez effectuer d’autres modifications que le fichier actuel banque indisponible, vous devez d’abord créer un nouveau partage. Ensuite, procédez comme suit :'
ms.openlocfilehash: 567db1e418d5c5c63af8e52146c5d6e1272d7677
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="move-file-store-data-to-a-new-file-store-in-skype-for-business-server-2015"></a>Déplacer des données de magasin de fichiers vers un nouveau magasin de fichiers dans Skype Entreprise Server 2015
 
Si vous devez supprimer le serveur de fichiers qui sert actuellement le stockage de fichiers de votre Skype pour le déploiement de Business Server 2015, ou si vous devez effectuer d’autres modifications que le fichier actuel banque indisponible, vous devez d’abord créer un nouveau partage. Ensuite, procédez comme suit :
  
1. Arrêtez le Skype pour les services Business Server 2015 qui utilisent le magasin de fichiers que vous souhaitez supprimer.
    
2. Définir l’emplacement du fichier dans le Générateur de topologies et publier les modifications pour libérer le nouveau fichier de stockage à votre déploiement.
    
3. Déplacez les données vers le nouveau magasin de fichiers.
    
4. Redémarrez les serveurs ou services.
    
5. Vous pouvez également supprimer les partages de fichiers et dossier de fichiers anciens.
    
### <a name="to-move-file-store-data-from-one-file-store-to-a-new-file-store"></a>Pour déplacer les données du magasin de fichiers d’un magasin de fichiers vers un autre

1. Ouvrez une session sur un ordinateur en tant que membre du groupe RTCUniversersalServerAdmins ou CsServerAdministrator, où le Skype pour Business Server 2015, outils d’administration sont installés.
    
2.  Ouvrir une fenêtre de navigateur et entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration de Business Server. 
    
3. Dans la barre de navigation de gauche, cliquez sur **Topologie**, puis sur **État**.  
    
4. Pour chaque pool de directeur, directeur, serveur Standard Edition et pool frontal qui utilise le magasin de fichiers que vous voulez supprimer, sélectionnez le serveur ou le pool, cliquez sur **Action**, puis cliquez sur **Arrêter tous les services**. 
    
5. Ouvrez une session sur l’ordinateur sur lequel le Générateur de topologie est installé en tant que membre du groupe Admins du domaine et du groupe RTCUniversalServerAdmins.
    
6. Démarrer le Générateur de topologies : Cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business Server 2015**, puis cliquez sur **Skype pour le Générateur de topologies Business Server 2015**.
    
7. Sélectionnez un serveur ou un pool qui utilise le magasin de fichiers et procédez comme suit :
    
   a. Cliquez avec le bouton droit sur le serveur ou le pool, puis cliquez sur **Modifier les propriétés**.  
    
   b. Dans **Modifier les propriétés**, sous **Associations**, puis sous **Magasin de fichiers**, cliquez sur **Nouveau**.
    
   c. Dans **Définir un nouveau magasin de fichiers**, sous **Nom de domaine complet du serveur de fichiers**, saisissez le nom de domaine complet du serveur de fichiers. Sous **Partage de fichiers**, saisissez le nom de dossier pour le nouveau partage de fichiers et cliquez sur **OK**.
    
    > [!IMPORTANT]
    > Cette étape définit une nouvelle banque de fichier à utiliser dans le Générateur de topologies. Définissez-le une seule fois, non pour chaque serveur. Avant de publier la topologie, vous devez créer le partage de fichiers sur le serveur de fichiers défini. Pour plus d’informations, consultez [définir le magasin de fichiers pour le Front-End](http://technet.microsoft.com/library/90994400-c4e5-4509-af41-121ac716fbca.aspx). 
  
8. Pour chaque serveur ou pool qui utilise le magasin de fichiers, procédez comme suit :
    
   a. Cliquez avec le bouton droit sur le serveur ou le pool, puis cliquez sur **Modifier les propriétés**.
    
   b. Dans **Modifier les propriétés**, sous **Associations**, dans **Magasin de fichiers**, sélectionnez le nouveau partage de fichiers, puis cliquez sur **OK**.
    
9. Publier la topologie et vérifier l’état de la réplication puis exécutez le Skype pour l’Assistant de déploiement de Business Server en fonction des besoins. Pour plus d’informations, reportez-vous à la section [Procédures courantes pour la suppression des serveurs Lync et composants](http://technet.microsoft.com/library/5438ce1e-57fa-4031-8bdb-3af6581d901b.aspx).
    
10. Démarrez une invite de commande : cliquez sur **Démarrer**, sur **exécuter**et tapez cmd.exe.
    
11. Dans la ligne de commande, tapez ce qui suit :
    
     ```
     Robocopy \\<OldFileServer>\<OldShare> \\<NewFileServer>\<NewShare> /S /R:10 /W:10 /XF Meeting.Active /MT /LOG:<directory path\logname>

     ```

    > [!TIP]
    > Le commutateur /S permet de copier sur des fichiers, des répertoires et des sous-répertoires. Le commutateur /XF permet d’ignorer des fichiers nommés Meeting.Active. Les versions actuelles du fichier robocopy.exe avec le commutateur /MT augmentent considérablement la vitesse de copie à l’aide de plusieurs threads. Pour le commutateur /LOG, utilisez un chemin et nom du fichier répertoire sous la forme de C:\Logfiles\log.txt. Ce commutateur crée un fichier journal d’opérations à l’emplacement nommé. 
  
12. Lors de la copie des données est terminée, dans le panneau de configuration de Lync Server, cliquez sur **la topologie**, puis cliquez sur **état**.
    
13. Pour chaque serveur et pool sur lesquels vous avez arrêté les services, sélectionnez le serveur ou pool, cliquez sur **Action**, puis sur **Démarrer tous les services**. 
    
14. Supprimez l’ancien magasin de fichiers de la topologie et publiez la topologie. Pour plus d’informations, voir [suppression d’un magasin de fichiers](http://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx).
    
15. (Facultatif) Connectez-vous à l’ordinateur qui contient le magasin de fichiers que vous venez de supprimer en tant que membre du groupe Administrateurs local ou du groupe Administrateurs de domaines et supprimez le partage de fichiers et le répertoire anciens.
    
## <a name="see-also"></a>Voir aussi


[Réaffecter un serveur à un autre magasin de fichiers](http://technet.microsoft.com/library/18509cce-a4d2-4537-a822-f99de6d7598e.aspx)
  
[Supprimer un fichier de magasin](http://technet.microsoft.com/library/1ba7eb15-5c87-4357-b4d8-f59409ac7f71.aspx)

