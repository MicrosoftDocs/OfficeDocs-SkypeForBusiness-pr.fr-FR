---
title: 'Lync Server 2013 : restauration d’un serveur Standard Edition Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a Standard Edition server
ms:assetid: d1845663-3138-4fd6-b3e7-337e294d40d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202190(v=OCS.15)
ms:contentKeyID: 51541519
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0ecc58dc2683cd07b83a8c57385593961c3e985
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723454"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-standard-edition-server-in-lync-server-2013"></a>Restauration d’un serveur Standard Edition Server dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-21_

Dans le cas contraire, suivez les procédures décrites dans cette section pour un serveur Standard Edition n’hébergeant pas le magasin central de gestion. Si la Banque centrale de gestion échoue, voir [restauration du serveur qui héberge le magasin de gestion central dans Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).

<div>


> [!TIP]  
> Nous vous recommandons de prendre une copie d’image du système avant de commencer la restauration. Vous pouvez utiliser cette image comme point de restauration en cas de problème de restauration. Vous souhaiterez peut-être prendre la copie d’image après l’installation du système d’exploitation et de SQL Server, puis restaurez ou Réinscrivez les certificats.



</div>

<div>

## <a name="to-restore-a-standard-edition-server"></a>Pour restaurer un serveur Standard Edition Server

1.  Commencez par un serveur propre ou nouveau qui porte le même nom de domaine complet (FQDN) que l’ordinateur en panne, installez le système d’exploitation, puis restaurez ou Réinscrivez les certificats.
    
    <div>
    

    > [!NOTE]  
    > Pour effectuer cette étape, suivez les procédures de déploiement du serveur de votre organisation.

    
    </div>

2.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins et du groupe administrateurs locaux, connectez-vous au serveur que vous restaurez.

3.  Restaurez le magasin de fichiers en copiant le magasin de fichiers approprié de $Backup à l’emplacement de stockage des fichiers sur le serveur et partagez le dossier.
    
    <div>
    

    > [!IMPORTANT]  
    > Le chemin d’accès et le nom de fichier du magasin de fichiers restauré doivent être identiques à ceux du magasin de fichiers sauvegardé pour que les composants qui les utilisent puissent y accéder.

    
    </div>

4.  Exécuter le générateur de topologie :
    
    1.  Démarrer le générateur de topologie : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Générateur de topologie de Lync Server**.
    
    2.  Cliquez sur **Télécharger la topologie à partir du déploiement existant**, puis cliquez sur **OK**.
    
    3.  Sélectionnez la topologie, puis cliquez sur **Enregistrer**. Cliquez sur **Oui** pour confirmer votre sélection.

5.  Recherchez le dossier d’installation ou le média de Lync Server, puis démarrez l’Assistant Déploiement de Lync Server \\situé\\à\\l’installation de Setup. exe. Utilisez l’Assistant Déploiement de Lync Server pour effectuer les opérations suivantes :
    
    1.  Exécutez l' **étape 1 : installer le magasin de configuration local** pour installer les fichiers de configuration locaux.
    
    2.  Exécutez l' **étape 2 : configurer ou supprimer les composants serveur Lync** pour installer les rôles serveur de Lync Server.
    
    3.  Exécutez l' **étape 3 : demandez, installez ou attribuez des certificats** pour attribuer les certificats.
    
    4.  Exécutez l' **étape 4 : démarrer des services** pour démarrer des services sur le serveur.
    
    Pour plus d’informations sur l’exécution de l’Assistant Déploiement, voir la documentation de déploiement pour le rôle de serveur que vous restaurez.

6.  Restaurez les données utilisateur en procédant comme suit :
    
    1.  Copiez ExportedUserData. zip de\\ $Backup dans un répertoire local.
    
    2.  Avant de restaurer les données utilisateur, vous devez arrêter les services Lync. Pour ce faire, tapez :
        
            Stop-CsWindowsService
    
    3.  Pour restaurer les données utilisateur, à partir de la ligne de commande, tapez :
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        Par exemple :
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  Redémarrez les services Lync en entrant :
        
            Start-CsWindowsService

7.  Si vous avez déployé Response Group sur ce serveur Standard Edition Server, restaurez les données de configuration du groupe de réponse. Pour plus d’informations, consultez la rubrique [restauration des paramètres du groupe de réponses dans Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).

8.  Si vous avez déployé une conversation persistante sur ce serveur Standard Edition Server, restaurez la base de données de chat permanent (MGC. mdf).
    
    Si vous avez utilisé la sauvegarde SQL Server pour sauvegarder la base de données de chat persistante, utilisez les procédures de restauration SQL Server pour la restaurer.
    
    Si vous avez utilisé l’applet de passe Export-CsPersistentChatData pour la sauvegarder, utilisez le fichier Import-CsPersistentChatData pour le restaurer.

</div>

</div>

<span> </span>

</div>

</div>

</div>

