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
ms.openlocfilehash: 906018941b00d8ef2cbb5e37aef8d1245ad93f00
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221438"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="administering-users-in-a-hybrid-lync-server-2013-deployment"></a>Administration des utilisateurs dans un déploiement hybride de Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-05-29_

Vous pouvez gérer les paramètres utilisateur et les stratégies pour les utilisateurs migrés vers Lync Online à l’aide des fonctionnalités de gestion des utilisateurs disponibles dans le centre d’administration 365 de Microsoft. Vous devez vous connecter à l’aide de votre compte d’administrateur client pour effectuer des tâches d’administration.

<div>

## <a name="moving-users-back-to-on-premises"></a>Redéplacement des utilisateurs vers l’organisation locale

<div class="">


> [!IMPORTANT]  
> Cette section s’applique uniquement aux utilisateurs qui ont été créés et activés pour Lync sur site, puis déplacés d’un déploiement local vers Lync Online. Si vous souhaitez déplacer des utilisateurs qui ont été créés dans Lync Online (et qui n’ont jamais été activés pour Lync dans un déploiement local), reportez-vous à la rubrique <A href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Moving users from Lync Online to Lync on-premises in Lync Server 2013</A>.



</div>

  - Exécutez les applets de commande suivantes pour déplacer un utilisateur de Lync Online vers Lync local :
    
       ```PowerShell
        $cred=Get-Credential
       ```
    
       ```PowerShell
        Move-CsUser -Identity username@contoso.com -Target localpool.contoso.com -Credential $cred -HostedMigrationOverrideUrl <URL>
       ```

Le format de l’URL spécifiée pour le paramètre **HostedMigrationOverrideUrl** doit être l’URL du pool où le service de migration hébergée est en cours d’exécution, au format suivant :

\<Nom de domaine complet du Pool https:// \> /HostedMigration/hostedmigrationService.svc. Vous pouvez déterminer l’URL du service de migration hébergée en affichant l’URL du panneau de configuration Lync Online pour votre compte d’organisation Microsoft 365 ou Office 365.

**Pour déterminer l’URL du service de migration hébergée pour votre organisation Microsoft 365 ou Office 365**

1.  Connectez-vous à votre organisation en tant qu’administrateur.

2.  Ouvrez le **Centre d’administration Lync**.

3.  Avec le **Centre d’administration Lync** affiché, sélectionnez et copiez l’URL dans la barre d’adresse jusqu’à **Lync.com**. Un exemple d’URL doit ressembler à ce qui suit :
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  Remplacez **webdir** dans l’URL par **administrateur**, de la façon suivante :
    
    `https://admin0a.online.lync.com`

5.  Ajoutez la chaîne suivante à l’URL : **/HostedMigration/hostedmigrationservice.svc**.
    
    L’URL résultante, qui est la valeur de **HostedMigrationOverrideUrl**, doit ressembler à ce qui suit :
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

</div>

<span> </span>

</div>

</div>

</div>

