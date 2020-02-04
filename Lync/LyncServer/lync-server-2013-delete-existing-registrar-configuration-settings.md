---
title: 'Lync Server 2013 : supprimer les paramètres de configuration du Bureau d’enregistrement existants'
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
ms.openlocfilehash: 960d0dd055ccf2f380b1ebf8124432da8daf6563
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763498"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-existing-registrar-configuration-settings-in-lync-server-2013"></a>Supprimer les paramètres de configuration du Bureau d’enregistrement existants dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Pour supprimer un bureau d’enregistrement, procédez comme suit.

<div>

## <a name="to-delete-registrar-configuration-settings"></a>Pour supprimer des paramètres de configuration du serveur d’inscriptions avancé

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou doté de droits d’utilisateur équivalents), ou affectées au rôle CsServerAdministrator ou CsAdministrator, connectez-vous à n’importe quel ordinateur se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Sécurité**, puis sur **Serveur d’inscriptions avancé**.

4.  Dans la page **Serveur d’inscriptions avancé**, dans le champ de recherche, tapez entièrement ou partiellement le nom du serveur d’inscriptions avancé à supprimer.

5.  Dans la liste, sélectionnez le serveur d’inscriptions avancé souhaité, cliquez sur **Modifier**, puis sur **Supprimer**.

6.  Cliquez sur **OK**.

</div>

<div>

## <a name="removing-registrar-configuration-settings-by-using-windows-powershell-cmdlets"></a>Suppression des paramètres de configuration du Bureau d’enregistrement à l’aide des cmdlets Windows PowerShell

Vous pouvez supprimer les paramètres de configuration du Bureau d’enregistrement à l’aide de Windows PowerShell et de l’applet de passe **Remove-CsProxyConfiguration** . Vous pouvez exécuter cette applet de commande sur Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell ».

<div>

## <a name="to-remove-a-specific-set-of-registrar-security-settings"></a>Pour supprimer un ensemble spécifique de paramètres de sécurité du serveur d’inscriptions avancé

  - La commande ci-dessous supprime les paramètres de sécurité du serveur d’inscriptions avancé appliqués au serveur Edge atl-edge-011.litwareinc.com :
    
        Remove-CsProxyConfiguration -Identity service:EdgeServer:atl-edge-011.litwareinc.com

</div>

<div>

## <a name="to-remove-all-of-the-registrar-security-settings-applied-to-the-site-scope"></a>Pour supprimer tous les paramètres de sécurité du serveur d’inscriptions avancé appliqués à l’étendue Site

  - La commande ci-dessous supprime tous les paramètres de sécurité du serveur d’inscriptions avancé appliqués au service de serveur d’inscriptions avancé :
    
        Get-CsProxyConfiguration -Filter "service:Registrar:*" | Remove-CsProxyConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-registrar-security-settings-that-allow-ntlm-authentication"></a>Pour supprimer tous les paramètres de sécurité du serveur d’inscriptions avancé qui permettent l’authentification NTLM

  - La commande ci-dessous supprime tous les paramètres de sécurité du serveur d’inscriptions avancé qui permettent l’utilisation de NTLM pour l’authentification client :
    
        Get-CsProxyConfiguration | Where-Object {$_.UseNtlmForClientToProxyAuth -eq $True}| Remove-CsProxyConfiguration

</div>

Pour plus d’informations, consultez la rubrique [Remove-CsProxyConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsProxyConfiguration).

</div>

</div>

<span> </span>

</div>

</div>

</div>

