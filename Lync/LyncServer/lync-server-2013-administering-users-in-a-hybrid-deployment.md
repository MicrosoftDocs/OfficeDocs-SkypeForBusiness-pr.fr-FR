---
title: 'Lync Server 2013 : administration des utilisateurs dans un déploiement hybride'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Administering users in a hybrid deployment
ms:assetid: 6924ed7b-30a9-4be7-b952-90655625f2c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204967(v=OCS.15)
ms:contentKeyID: 48184381
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e416901fd5a98ffa3974c29e469eef2b6f4cb783
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737964"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="administering-users-in-a-hybrid-lync-server-2013-deployment"></a>Administration des utilisateurs dans un déploiement 2013 Lync Server hybride

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-05-29_

Vous pouvez gérer les paramètres utilisateur et les stratégies pour les utilisateurs migrés vers Lync Online à l’aide des fonctionnalités de gestion des utilisateurs disponibles sur le portail en ligne Microsoft Office 365. Vous devez vous connecter à l’aide d’un compte d’administrateur client pour effectuer des tâches d’administration.

<div>

## <a name="moving-users-back-to-on-premises"></a>Replacer les utilisateurs sur le serveur local

<div class="">


> [!IMPORTANT]  
> Cette section s’applique uniquement aux utilisateurs qui ont été créés et activés pour Lync local, puis transférés d’un déploiement local vers Lync Online. Pour déplacer des utilisateurs qui ont été créés dans Lync Online (et qui ne sont pas encore activés pour Lync dans un déploiement local), voir <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">déplacement des utilisateurs de Lync Online vers Lync local dans Lync Server 2013</A>.



</div>

  - Pour déplacer un utilisateur de Lync Online vers Lync local, exécutez les applets de commande suivantes :
    
       ```PowerShell
        $cred=Get-Credential
       ```
    
       ```PowerShell
        Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
       ```

L’URL spécifiée pour le paramètre **HostedMigrationOverrideUrl** doit correspondre à celle du pool dans lequel le service de migration hébergée est exécuté, au format suivant :

Nom\<de domaine\>complet (FQDN) du pool https:///HostedMigration/hostedmigrationService.svc. Vous pouvez déterminer l’URL du service de migration hébergée en affichant l’URL du Panneau de configuration Lync Online correspondant à votre compte client Office 365.

**Pour déterminer l’URL du service de migration hébergée de votre client Office 365**

1.  Connectez-vous à votre client Office 365 en tant qu’administrateur.

2.  Ouvrez le **Centre d’administration Lync**.

3.  Avec le **Centre d’administration Lync** affiché, sélectionnez et copiez l’URL dans la barre d’adresses jusqu’à **Lync.com**. L’URL doit se présenter comme dans l’exemple suivant :
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  Dans l’URL, remplacez **webdir** par **admin** pour obtenir le résultat suivant :
    
    `https://admin0a.online.lync.com`

5.  Ajoutez la chaîne ci-dessous à l’URL : **/HostedMigration/hostedmigrationservice.svc**.
    
    L’URL obtenue, qui est la valeur de **HostedMigrationOverrideUrl**, doit se présenter comme suit :
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

</div>

<span> </span>

</div>

</div>

</div>

