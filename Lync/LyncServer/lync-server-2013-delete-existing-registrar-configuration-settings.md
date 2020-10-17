---
title: 'Lync Server 2013 : suppression des paramètres de configuration du serveur d’inscriptions existants'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete existing Registrar configuration settings
ms:assetid: ae43cd75-cae4-4f78-b037-779a2cdb583b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182571(v=OCS.15)
ms:contentKeyID: 48185132
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a0624806ba8ed2f10bc0c7cffbf1e8879209c66
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525601"
---
# <a name="delete-existing-registrar-configuration-settings-in-lync-server-2013"></a>Supprimer les paramètres de configuration du serveur d’inscriptions existants dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Suivez ces étapes pour supprimer un serveur d’inscriptions.

<div>

## <a name="to-delete-registrar-configuration-settings"></a>Pour supprimer les paramètres de configuration du serveur d’inscriptions

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Sécurité**, puis sur **Serveur d’inscriptions**.

4.  Dans la page **Serveur d’inscriptions**, dans le champ de recherche, tapez entièrement ou partiellement le nom du serveur d’inscriptions que vous voulez supprimer.

5.  Dans la liste, cliquez sur le serveur d’inscriptions souhaité, cliquez sur **Modifier**, puis sur **Supprimer**.

6.  Cliquez sur **OK**.

</div>

<div>

## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a>Suppression des paramètres de configuration du serveur d’inscriptions à l’aide des applets de commande Windows PowerShell

Vous pouvez supprimer les paramètres de configuration du serveur d’inscriptions à l’aide de Windows PowerShell et de l’applet de commande **Remove-CsProxyConfiguration** . Vous pouvez exécuter cette applet de commande à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-remove-a-specific-set-of-registrar-security-settings"></a>Pour supprimer un ensemble spécifique de paramètres de sécurité du serveur d’inscriptions avancé

  - La commande suivante supprime les paramètres de sécurité du serveur d’inscriptions avancé appliqués au serveur Edge atl-edge-011.litwareinc.com :
    
        Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com

</div>

<div>

## <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a>Pour supprimer tous les paramètres de sécurité du serveur d’inscriptions avancé appliqués l’étendue Site

  - La commande suivante supprime tous les paramètres de sécurité du serveur d’inscriptions avancé appliqués au service de serveur d’inscriptions avancé :
    
        Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a>Pour supprimer tous les paramètres de sécurité du serveur d’inscriptions avancé qui permettent l’authentification NTLM

  - La commande suivante supprime tous les paramètres de sécurité du serveur d’inscriptions avancé qui permettent l’utilisation de NTLM pour l’authentification client :
    
        Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration

</div>

Pour plus d’informations, consultez la rubrique [Remove-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsProxyConfiguration).

</div>

</div>

<span> </span>

</div>

</div>

</div>

