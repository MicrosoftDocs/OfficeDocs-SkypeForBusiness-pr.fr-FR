---
title: 'Lync Server 2013 : suppression d’une stratégie de code confidentiel'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a PIN policy
ms:assetid: 7c378927-2e41-418e-9721-327021bd2e45
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521020(v=OCS.15)
ms:contentKeyID: 48184609
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d4c64b5490e53c8ba51f7832cef9ba483b1760d1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525641"
---
# <a name="delete-a-pin-policy-in-lync-server-2013"></a>Supprimer une stratégie de code confidentiel dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Suivez cette procédure pour supprimer une stratégie de code confidentiel (PIN).

<div>


> [!NOTE]  
> Vous ne pouvez pas supprimer la stratégie de code confidentiel globale.



</div>

<div>

## <a name="to-delete-a-pin-policy-in-lync-server-2013-control-panel"></a>Pour supprimer une stratégie de code confidentiel dans le panneau de configuration Lync Server 2013

1.  À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Sécurité**, puis sur **Stratégie de code confidentiel**.

4.  Dans la page **Stratégie de code confidentiel**, dans le champ de recherche, tapez entièrement ou partiellement le nom de la stratégie à supprimer.

5.  Dans la liste des stratégies, cliquez sur la stratégie que vous souhaitez supprimer, cliquez sur **Modifier**, puis sur **Supprimer**.

6.  Cliquez sur **OK**.

</div>

<div>

## <a name="removing-pin-policies-by-using-windows-powershell-cmdlets"></a>Suppression de stratégies de code confidentiel à l’aide des applets de commande Windows PowerShell

Vous pouvez supprimer des stratégies de code confidentiel à l’aide de Windows PowerShell et de l’applet de commande Remove-CsPinPolicy. Vous pouvez exécuter cette cmdlet à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-remove-a-specific-pin-policy"></a>Pour supprimer une stratégie de code confidentiel spécifique

  - Cette commande supprime la stratégie de code confidentiel avec l’identité RedmondPinPolicy :
    
        Remove-CsPinPolicy -Identity "RedmondPinPolicy"

</div>

<div>

## <a name="to-remove-all-the-pin-policies-applied-to-the-site-scope"></a>Pour supprimer toutes les stratégies de code confidentiel appliquées à l’étendue du site

  - Cette commande supprime toutes les stratégies de code confidentiel configurées au niveau du site :
    
        Get-CsPinPolicy -Filter "site:*" | Remove-CsPinPolicy

</div>

<div>

## <a name="to-remove-all-the-pin-policies-that-allow-the-use-of-common-patterns"></a>Pour supprimer toutes les stratégies de code confidentiel qui autorisent l’utilisation de modèles courants

  - Cette commande supprime toutes les stratégies de code confidentiel qui autorisent l’utilisation de critères communs : G
    
        et-CsPinPolicy | Where-Object {$_.AllowCommonPatterns -eq $True} | Remove-CsPinPolicy

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Remove-applet cspinpolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsPinPolicy) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

