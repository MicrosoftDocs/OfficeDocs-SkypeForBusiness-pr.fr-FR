---
title: 'Lync Server 2013 : déplacer des utilisateurs vers Lync Online'
description: 'Lync Server 2013 : déplacer des utilisateurs vers Lync Online.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Move users to Lync Online
ms:assetid: 6a523c86-2eac-4fa4-973a-4406872c9a7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204969(v=OCS.15)
ms:contentKeyID: 48184392
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 501eda3a76cec3226831c0af3631317377cd82cb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541988"
---
# <a name="move-users-to-lync-online-in-lync-server-2013"></a>Déplacer des utilisateurs vers Lync Online dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-05-29_

Avant de commencer la migration des utilisateurs vers Lync Online, vous devez sauvegarder les données utilisateur associées aux comptes à déplacer. Toutes les données utilisateur ne sont pas déplacées avec le compte d’utilisateur. Pour plus d’informations, consultez la rubrique [Configuration requise pour la sauvegarde et la restauration dans Lync Server 2013 : Data](lync-server-2013-backup-and-restoration-requirements-data.md).

<div>

## <a name="migrate-user-settings-to-lync-online"></a>Migrer les paramètres utilisateur vers Lync Online

Les paramètres utilisateur sont déplacés avec le compte d’utilisateur. Certains paramètres locaux ne sont pas déplacés avec le compte d’utilisateur.

</div>

<div>

## <a name="moving-pilot-users-to-lync-online"></a>Migration des utilisateurs pilotes vers Lync Online

Avant de commencer à déplacer des utilisateurs vers Lync Online, vous souhaiterez peut-être déplacer quelques utilisateurs pilotes afin de vérifier que votre environnement est correctement configuré. Vous pouvez ensuite vérifier que les fonctionnalités et services de Lync fonctionnent comme prévu avant de tenter de déplacer des utilisateurs supplémentaires.

Pour déplacer un utilisateur local vers votre client Lync Online, exécutez les applets de commande suivantes dans Lync Server Management Shell à l’aide des informations d’identification d’administrateur de votre organisation Microsoft 365 ou Office 365. Remplacez « username@contoso.com » par les informations de l’utilisateur que vous souhaitez déplacer.

   ```PowerShell
    $creds=Get-Credential
   ```

   ```PowerShell
    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>
   ```

Le format de l’URL spécifiée pour le paramètre **HostedMigrationOverrideUrl** doit être l’URL du pool où le service de migration hébergée est en cours d’exécution, au format suivant : https:// \<Pool FQDN\> /HostedMigration/hostedmigrationService.svc.

Vous pouvez déterminer l’URL du service de migration hébergée en affichant l’URL du panneau de configuration Lync Online pour votre compte d’organisation Microsoft 365 ou Office 365.

**Pour déterminer l’URL du service de migration hébergée pour votre organisation**

1.  Connectez-vous à votre organisation Microsoft 365 ou Office 365 en tant qu’administrateur.

2.  Ouvrez le **Centre d’administration Lync**.

3.  Avec le **Centre d’administration Lync** affiché, sélectionnez et copiez l’URL dans la barre d’adresse jusqu’à **Lync.com**. Un exemple d’URL doit ressembler à ce qui suit :
    
    `https://webdir0a.online.lync.com/lscp/?language=en-US&tenantID=`

4.  Remplacez **webdir** dans l’URL par **administrateur**, de la façon suivante :
    
    `https://admin0a.online.lync.com`

5.  Ajoutez la chaîne suivante à l’URL : **/HostedMigration/hostedmigrationservice.svc**.
    
    L’URL résultante, qui est la valeur de **HostedMigrationOverrideUrl**, doit ressembler à ce qui suit :
    
    `https://admin0a.online.lync.com/HostedMigration/hostedmigrationservice.svc`

</div>

<div>

## <a name="moving-users-to-lync-online"></a>Migration des utilisateurs vers Lync Online

Vous pouvez déplacer plusieurs utilisateurs à l’aide de la cmdlet [Get-Csuser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) avec le paramètre – Filter pour sélectionner les utilisateurs avec une propriété spécifique affectée aux comptes d’utilisateur, comme RegistrarPool. Vous pouvez ensuite rediriger les utilisateurs renvoyés vers l’applet de commande [Move-Csuser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) , comme indiqué dans l’exemple suivant.

    Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>

Vous pouvez également utiliser le paramètre – OU pour récupérer tous les utilisateurs dans l’unité d’organisation spécifiée, comme illustré dans l’exemple suivant.

    Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds -HostedMigrationOverrideUrl <URL>

</div>

<div>

## <a name="verify-lync-online-user-settings-and-features"></a>Vérifier les paramètres et les fonctionnalités de l’utilisateur Lync Online

Pour vérifier que l’utilisateur a été déplacé correctement, procédez comme suit :

  - Affichez l’état de l’utilisateur dans le panneau de configuration Lync Online. L’indicateur visuel pour les utilisateurs locaux et les utilisateurs en ligne est différent.

  - Exécutez la l’applet commande suivant :
    
        Get-CsUser -Identity

</div>

</div>

<span> </span>

</div>

</div>

</div>

