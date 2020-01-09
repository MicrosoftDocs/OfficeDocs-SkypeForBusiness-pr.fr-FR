---
title: 'Lync Server 2013 : déplacer des utilisateurs vers Lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Move users to Lync Online
ms:assetid: 6a523c86-2eac-4fa4-973a-4406872c9a7d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204969(v=OCS.15)
ms:contentKeyID: 48184392
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6172c526816a3572d6c364b714d5d4e7e5323cac
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991369"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-users-to-lync-online-in-lync-server-2013"></a>Déplacer des utilisateurs vers Lync Online dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-05-29_

Avant de commencer à migrer des utilisateurs vers Lync Online, il est recommandé de sauvegarder les données utilisateur associées aux comptes à déplacer. Les données utilisateur ne sont pas toutes déplacées avec le compte d’utilisateur. Pour plus d’informations, reportez-vous à [Configuration requise pour la sauvegarde et la restauration dans Lync Server 2013 : données](lync-server-2013-backup-and-restoration-requirements-data.md).

<div>

## <a name="migrate-user-settings-to-lync-online"></a>Migration des paramètres utilisateur vers Lync Online

Les paramètres utilisateur sont déplacés en même temps que le compte d’utilisateur. Certains paramètres locaux ne sont pas déplacés avec le compte d’utilisateur.

</div>

<div>

## <a name="moving-pilot-users-to-lync-online"></a>Déplacement d’utilisateurs pilotes vers Lync Online

Avant de commencer à déplacer des utilisateurs vers Lync Online, vous souhaiterez peut-être déplacer quelques utilisateurs du programme pilote pour vérifier que votre environnement est correctement configuré. Vous pouvez ensuite vérifier la fonction et les fonctionnalités de Lync comme prévu avant d’essayer de déplacer d’autres utilisateurs.

Pour déplacer un utilisateur sur site vers votre client Lync Online, exécutez les applets de commande suivantes dans Lync Server Management Shell, à l’aide des informations d’identification d’administrateur de votre client Microsoft Office 365. Remplacez « nomutilisateur@contoso.com » par les informations de l’utilisateur à déplacer.

   ```PowerShell
    $creds=Get-Credential
   ```

   ```PowerShell
    Move-CsUser -Identity username@contoso.com -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>
   ```

Le format de l’URL spécifiée pour le paramètre **hostedmigrationoverrideurl doit correspondre** doit être l’URL du pool sur lequel le service de migration hébergé est en cours d’exécution, au format\<suivant :\>nom de domaine complet du pool https:///HostedMigration/hostedmigrationService.svc.

Vous pouvez déterminer l’URL du service de migration hébergée en affichant l’URL du Panneau de configuration Lync Online correspondant à votre compte client Office 365.

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

<div>

## <a name="moving-users-to-lync-online"></a>Déplacement d’utilisateurs vers Lync Online

Vous pouvez déplacer plusieurs utilisateurs à l’aide de l’applet de requête [Get-Csuser](https://docs.microsoft.com/powershell/module/skype/Get-CsUser) avec le paramètre-Filter pour sélectionner les utilisateurs ayant une propriété spécifique affectée aux comptes d’utilisateurs, par exemple, RegistrarPool. Vous pouvez ensuite canaler les utilisateurs retournés vers l’applet de commande [Move-Csuser](https://docs.microsoft.com/powershell/module/skype/Move-CsUser) , comme le montre l’exemple suivant.

    Get-CsUser -Filter {UserProperty -eq "UserPropertyValue"} | Move-CsUser -Target sipfed.online.lync.com -Credential $creds -HostedMigrationOverrideUrl <URL>

Vous pouvez également utiliser le paramètre –OU pour extraire tous les utilisateurs de l’unité d’organisation spécifiée, comme indiqué dans l’exemple suivant.

    Get-CsUser -OU "cn=hybridusers,cn=contoso.." | Move-CsUser -Target sipfed.online.lync.com -Credentials $creds -HostedMigrationOverrideUrl <URL>

</div>

<div>

## <a name="verify-lync-online-user-settings-and-features"></a>Vérifier les fonctionnalités et paramètres utilisateur de Lync Online

Vous pouvez vérifier que le déplacement d’un utilisateur a réussi des deux manières suivantes :

  - Affichez l’état de l’utilisateur dans le panneau de configuration Lync Online. L’indicateur visuel des utilisateurs locaux et des utilisateurs en ligne est différent.

  - Exécutez l’applet de commande suivante :
    
        Get-CsUser -Identity

</div>

</div>

<span> </span>

</div>

</div>

</div>

