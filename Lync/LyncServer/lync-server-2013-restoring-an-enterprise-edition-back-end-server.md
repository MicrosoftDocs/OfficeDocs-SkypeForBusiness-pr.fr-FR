---
title: 'Lync Server 2013 : restauration d’un serveur principal Enterprise Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring an Enterprise Edition Back End Server
ms:assetid: 1450eb4e-3315-4d02-8f02-6e1791fb1550
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202163(v=OCS.15)
ms:contentKeyID: 51541446
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 429bf681e157beece170b9fe10e64fa8dea749ef
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051116"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-an-enterprise-edition-back-end-server-in-lync-server-2013"></a>Restauration d’un serveur principal Enterprise Edition dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-18_

Utilisez la procédure décrite dans cette rubrique dans les deux cas suivants :

  - Les bases de données principale et miroir d’un serveur principal Enterprise Edition mis en miroir échouent.

  - Un serveur principal Enterprise Edition qui n’est pas mis en miroir échoue.

Si vous disposez d’un serveur principal Enterprise Edition en miroir et que seule la base de données miroir ou principale échoue, reportez-vous à la rubrique [restauration d’un serveur principal Enterprise Edition en miroir dans Lync server 2013-principal](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-primary.md) pour la restauration de la base de données principale et [restauration d’un serveur principal Enterprise Edition en miroir dans Lync Server 2013-miroir](lync-server-2013-restoring-a-mirrored-enterprise-edition-back-end-server-mirror.md) pour restaurer le miroir.

Si le magasin central de gestion échoue, consultez [la rubrique restauration du serveur qui héberge le magasin central de gestion dans Lync server 2013](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md). Si un serveur membre Enterprise Edition qui n’est pas le serveur principal échoue, consultez la rubrique [restauration d’un serveur membre Enterprise Edition dans Lync server 2013](lync-server-2013-restoring-an-enterprise-edition-member-server.md).

<div>


> [!TIP]  
> Nous vous recommandons de prendre une copie de l’image du système avant de commencer la restauration. Vous pouvez utiliser cette image comme point de restauration, en cas de problème lors de la restauration. Vous pouvez utiliser la copie d’image après avoir installé le système d’exploitation et SQL Server, et restaurer ou réinscrire les certificats.



</div>

<div>

## <a name="to-restore-an-enterprise-edition-back-end-server"></a>Pour restaurer un serveur principal Enterprise Edition

1.  Démarrez avec un serveur nouveau ou propre qui a le même nom de domaine complet (FQDN) que l’ordinateur défaillant, installez le système d’exploitation, puis restaurez ou Réinscrivez les certificats.
    
    <div>
    

    > [!NOTE]  
    > Suivez les procédures de déploiement de serveur de votre organisation pour effectuer cette étape.

    
    </div>

2.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins, connectez-vous au serveur que vous restaurez.

3.  Installez SQL Server 2012 ou SQL Server 2008 R2, en conservant les mêmes noms d’instance qu’avant la défaillance.
    
    <div>
    

    > [!NOTE]  
    > En fonction de votre déploiement, le serveur principal peut inclure plusieurs bases de données colocalisées ou distinctes. Suivez la même procédure pour installer SQL Server que celle que vous avez utilisée à l’origine pour déployer le serveur, avec les autorisations et les comptes de connexion SQL Server.

    
    </div>

4.  Après avoir installé SQL Server, procédez comme suit :
    
    1.  Démarrez le Générateur de topologie : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Générateur de topologie Lync Server**.
    
    2.  Cliquez sur **Télécharger la topologie à partir d’un déploiement existant**, puis cliquez sur **OK**.
    
    3.  Sélectionnez la topologie, puis cliquez sur **Enregistrer**. Cliquez sur **Oui** pour confirmer votre sélection.
    
    4.  Cliquez avec le bouton droit sur le nœud **Lync Server 2013** , puis cliquez sur **publier la topologie**.
    
    5.  Suivez l’Assistant **Publication de la topologie**. Sur la page **créer des bases de données** , sélectionnez les bases de données que vous souhaitez recréer.
        
        <div>
        

        > [!NOTE]  
        > Seules les bases de données autonomes s’affichent dans la page <STRONG>Créer des bases de données</STRONG>.

        
        </div>
    
    6.  Si vous restaurez un serveur principal qui a été mis en miroir, continuez à suivre le reste de l’Assistant jusqu’à ce que l’invite **créer une base de données miroir** s’affiche. Sélectionnez la base de données que vous souhaitez installer et terminez le processus.
    
    7.  Suivez le reste de l’Assistant, puis cliquez sur **Terminer**.
    
    <div>
    

    > [!TIP]  
    > Au lieu d’exécuter le générateur de topologie, vous pouvez utiliser l’applet de commande <STRONG>install-applet csdatabase</STRONG> pour créer chaque base de données et la cmdlet <STRONG>install-CsMirrorDatabase</STRONG> pour configurer la mise en miroir. Pour plus d’informations, voir la documentation Lync Server Management Shell.

    
    </div>

5.  Restaurez les données utilisateur en effectuant ce qui suit :
    
    1.  Copiez ExportedUserData. zip de\\ $Backup dans un répertoire local.
    
    2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.
    
    3.  Avant de restaurer les données utilisateur, vous devez arrêter Lync services. Pour ce faire, tapez :
        
            Stop-CsWindowsService
    
    4.  Pour restaurer les données utilisateur, à la ligne de commande, tapez :
        
            Import-CsUserData -PoolFqdn <Fqdn> -FileName <String>
        
        Par exemple :
        
            Import-CsUserData -PoolFqdn "atl0cs-001.litwareinc.com" -FileName "C:\Logs\ExportedUserDatal.zip"
    
    5.  Redémarrez Lync services en tapant :
        
            Start-CsWindowsService

6.  Si vous avez déployé Response Group sur ce pool, restaurez les données de configuration du groupe Response Group. Pour plus d’informations, reportez-vous à la rubrique [restauration des paramètres de Response Group dans Lync Server 2013](lync-server-2013-restoring-response-group-settings.md).

7.  Si vous restaurez un serveur principal qui inclut des bases de données d’archivage ou de surveillance, restaurez les données d’archivage ou de surveillance à l’aide d’un outil SQL Server, tel que SQL Server Management Studio. Pour plus d’informations, reportez-vous à la rubrique [restauration des données de surveillance ou d’archivage dans Lync Server 2013](lync-server-2013-restoring-monitoring-or-archiving-data.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

