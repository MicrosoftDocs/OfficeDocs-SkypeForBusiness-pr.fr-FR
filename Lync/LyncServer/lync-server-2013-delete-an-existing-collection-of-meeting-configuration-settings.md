---
title: Supprimer une collection existante de paramètres de configuration de réunion
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of meeting configuration settings
ms:assetid: 92ff8a91-05c5-4047-a533-5dff12f22299
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688136(v=OCS.15)
ms:contentKeyID: 49733736
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: edf416af31b219c07691790b88d672d26768104d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514661"
---
# <a name="delete-an-existing-collection-of-meeting-configuration-settings-in-lync-server-2013"></a>Supprimer une collection existante de paramètres de configuration de réunion dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Vous pouvez supprimer une configuration de site ou utilisateur. La configuration globale ne peut pas être supprimée. Si vous supprimez la configuration globale, ses valeurs par défaut sont automatiquement rétablies.

<div>

## <a name="to-delete-a-site-or-user-meeting-configuration"></a>Pour supprimer une configuration de réunion utilisateur ou de site

1.  Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Configuration de la réunion**.

4.  Dans la liste des configurations de réunion, cliquez sur la configuration de site ou de pool que vous souhaitez supprimer, cliquez sur **modifier**, puis cliquez sur **supprimer**.

</div>

<div>

## <a name="removing-meeting-configuration-settings-by-using-windows-powershell-cmdlets"></a>Suppression des paramètres de configuration de réunion à l’aide des applets de commande Windows PowerShell

Les paramètres de réunion peuvent être supprimés à l’aide de Windows PowerShell et de l’applet de commande Remove-CsMeetingConfiguration. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-remove-a-specified-collection-of-meeting-configuration-settings"></a>Pour supprimer une collection spécifiée de paramètres de configuration de réunion

  - Cette commande supprime les paramètres de configuration de réunion appliqués au site Redmond :
    
        Remove-CsMeetingConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-meeting-configuration-settings-applied-to-the-site-scope"></a>Pour supprimer tous les paramètres de configuration de réunion appliqués à l’étendue site

  - Cette commande supprime tous les paramètres de configuration de réunion appliqués au niveau du site :
    
        Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration

</div>

<div>

## <a name="to-remove-all-the-meeting-configuration-settings-that-admit-anonymous-users-by-default"></a>Pour supprimer tous les paramètres de configuration de réunion qui autorisent les utilisateurs anonymes par défaut

  - Et cette commande supprime tous les paramètres qui autorisent l’admission des utilisateurs anonymes par défaut :
    
        Get-CsMeetingConfiguration | Where-Object {$_.AdmitAnonymousUsersByDefault -eq $True} | Remove-CsMeetingConfiguration

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Remove-CsMeetingConfiguration](https://technet.microsoft.com/library/Gg412775(v=OCS.15)) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

