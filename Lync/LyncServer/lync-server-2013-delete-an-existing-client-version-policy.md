---
title: 'Lync Server 2013 : suppression d’une stratégie de version de client existante'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing client version policy
ms:assetid: b88aaa25-97ff-4eb6-bd34-b97332cd6890
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ923064(v=OCS.15)
ms:contentKeyID: 50675349
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d74fa95a92c483d5a37c3f051d6dc372110a00b9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147617"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-client-version-policy-in-lync-server-2013"></a>Supprimer une stratégie de version de client existante dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Si vous souhaitez supprimer une stratégie de version de client précédemment configurée, vous pouvez la supprimer du panneau de configuration Lync Server 2013 ou de Lync Server 2013 Management Shell.

<div>

## <a name="to-delete-client-version-policies-by-using-lync-server-control-panel"></a>Pour supprimer des stratégies de version du client à l’aide du panneau de configuration Lync Server

1.  Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **clients**, puis sur le bouton de navigation **stratégie de version du client** .

4.  Sur la page **stratégie de version du client** , sélectionnez la ou les stratégies de version du client que vous souhaitez supprimer, cliquez sur **modifier**, puis sur **supprimer**.

</div>

<div>

## <a name="deleting-client-version-policies-by-using-windows-powershell-cmdlets"></a>Suppression des stratégies de version du client à l’aide des applets de commande Windows PowerShell

Vous pouvez supprimer des stratégies de version du client à l’aide de l’applet de commande **Remove-CsClientVersionPolicy** . Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.

<div>

## <a name="to-remove-a-specific-client-version-policy"></a>Pour supprimer une stratégie de version de client spécifique

  - Cette commande supprime la stratégie de version du client appliquée au site Redmond :
    
        Remove-CsClientVersionPolicy -Identity site:Redmond

</div>

<div>

## <a name="to-remove-all-the-client-version-policies-applied-to-the-site-scope"></a>Pour supprimer toutes les stratégies de version du client appliquées à l’étendue du site

  - Cette commande permet de supprimer toutes les stratégies de version des clients configurées au niveau de l’étendue du site :
    
        Get-CsClientVersionPolicy -Fiter "site:*" | Remove-CsClientVersionPolicy

</div>

<div>

## <a name="to-remove-client-version-policies-that-do-not-include-a-specific-user-agent"></a>Pour supprimer des stratégies de version du client qui n’incluent pas d’agent utilisateur spécifique

  - Cette commande supprime toutes les stratégies de version du client qui n’incluent pas de règle pour l’agent utilisateur Windows Phone Lync (WPLync) :
    
        Get-CsClientVersionPolicy | Where-Object {$_.Rules -notmatch "UserAgent=WPLync" | Remove-CsClientVersionPolicy

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Remove-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsClientVersionPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

