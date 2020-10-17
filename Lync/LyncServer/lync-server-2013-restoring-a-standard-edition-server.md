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
ms.openlocfilehash: 479e4c690d0ca7931631f3bc553d1dafc2a10ea7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511561"
---
# <a name="restoring-a-standard-edition-server-in-lync-server-2013"></a>Restauration d’un serveur Standard Edition Server dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-21_

Si un serveur Standard Edition Server qui n’héberge pas le magasin central de gestion échoue, suivez les procédures décrites dans cette section. Si le magasin central de gestion échoue, consultez [la rubrique restauration du serveur qui héberge le magasin central de gestion dans Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md).

<div>


> [!TIP]  
> Nous vous recommandons de prendre une copie de l’image du système avant de commencer la restauration. Vous pouvez utiliser cette image comme point de restauration, en cas de problème lors de la restauration. Vous pouvez créer la copie image après avoir installé le système d’exploitation et SQL Server, puis restaurer ou réinscrire les certificats.



</div>

<div>

## <a name="to-restore-a-standard-edition-server"></a>Pour restaurer un serveur Standard Edition

1.  Démarrez avec un serveur nouveau ou propre qui a le même nom de domaine complet (FQDN) que l’ordinateur défaillant, installez le système d’exploitation, puis restaurez ou Réinscrivez les certificats.
    
    <div>
    

    > [!NOTE]  
    > Suivez les procédures de déploiement de serveur de votre organisation pour effectuer cette étape.

    
    </div>

2.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins et du groupe Administrateurs local, ouvrez une session sur le serveur que vous restaurez.

3.  Restaurez le magasin de fichiers en copiant le magasin de fichiers approprié à partir de $Backup vers l’emplacement du magasin de fichiers sur le serveur et partagez le dossier.
    
    <div>
    

    > [!IMPORTANT]  
    > Le chemin d’accès et le nom de fichier du magasin de fichiers restauré doivent être identiques à ceux du magasin de fichiers sauvegardé afin que les composants qui utilisent les fichiers puissent y accéder.

    
    </div>

4.  Exécutez le générateur de topologie :
    
    1.  Démarrez le Générateur de topologie : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Générateur de topologie Lync Server**.
    
    2.  Cliquez sur **Télécharger la topologie à partir d’un déploiement existant**, puis cliquez sur **OK**.
    
    3.  Sélectionnez la topologie, puis cliquez sur **Enregistrer**. Cliquez sur **Oui** pour confirmer votre sélection.

5.  Naviguez jusqu’au dossier ou au support d’installation de Lync Server, puis démarrez l’Assistant Déploiement de Lync Server situé lors de l' \\ installation de \\ amd64 \\Setup.exe. Utilisez l’Assistant Déploiement de Lync Server pour effectuer les opérations suivantes :
    
    1.  Exécutez l’**Étape 1 : Installer le magasin de configurations local** pour installer les fichiers de configuration locaux.
    
    2.  Exécutez l' **étape 2 : installer ou supprimer des composants Lync Server** pour installer les rôles serveur Lync Server.
    
    3.  Exécuter l’**Étape 3 : Demander, installer ou assigner les certificats** pour assigner les certificats.
    
    4.  Exécutez l’**Étape 4 : Démarrer les services** pour démarrer les services sur le serveur.
    
    Pour plus d’informations sur l’exécution de l’Assistant Déploiement, voir la documentation de déploiement relative au rôle serveur que vous restaurez.

6.  Restaurez les données utilisateur en effectuant ce qui suit :
    
    1.  Copiez ExportedUserData.zip de $Backup \\ vers un répertoire local.
    
    2.  Avant de restaurer les données utilisateur, vous devez arrêter Lync services. Pour ce faire, tapez :
        
            Stop-CsWindowsService
    
    3.  Pour restaurer les données utilisateur, à la ligne de commande, tapez :
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        Par exemple :
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    4.  Redémarrez Lync services en tapant :
        
            Start-CsWindowsService

7.  Si vous avez déployé Response Group sur ce serveur Standard Edition, restaurez les données de configuration Response Group. Pour plus d’informations, reportez-vous à la rubrique [restauration des paramètres de Response Group dans Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).

8.  Si vous avez déployé une conversation permanente sur ce serveur Standard Edition, restaurez la base de données de conversation permanente (MGC. mdf).
    
    Si vous avez utilisé la sauvegarde SQL Server pour sauvegarder la base de données de conversation permanente, utilisez les procédures de restauration SQL Server pour la restaurer.
    
    Si vous avez utilisé l’applet de commande Export-CsPersistentChatData pour la sauvegarder, utilisez la Import-CsPersistentChatData pour la restaurer.

</div>

</div>

<span> </span>

</div>

</div>

</div>

