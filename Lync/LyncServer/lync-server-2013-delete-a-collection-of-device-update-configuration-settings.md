---
title: 'Lync Server 2013 : suppression d’une collection de paramètres de configuration de mise à jour des périphériques'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete a collection of Device Update configuration settings
ms:assetid: 1a649136-34a9-42a7-a5b3-a78bbfe93f36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994019(v=OCS.15)
ms:contentKeyID: 51803928
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 345e1ad4c621ce6330b1b1a34c97664d080d6575
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044066"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-collection-of-device-update-configuration-settings-in-lync-server-2013"></a>Supprimer une collection de paramètres de configuration de mise à jour des périphériques dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-20_

Les paramètres de configuration de mise à jour des périphériques peuvent également être supprimés à l’aide de Windows PowerShell et de l’applet de commande **Remove-CsdeviceUpdateConfiguration** . Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.

<div>


<div>

## <a name="to-remove-a-specific-collection-of-device-update-configuration-settings"></a>Pour supprimer une collection spécifique de paramètres de configuration de mise à jour de périphériques

  - Cette commande supprime les paramètres de configuration de mise à jour des périphériques appliqués au site Redmond :
    
        Remove-CsDeviceUpdateConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-device-update-configuration-settings-applied-to-the-site-scope"></a>Pour supprimer tous les paramètres de configuration de mise à jour des périphériques appliqués à l’étendue site

  - Cette commande supprime tous les paramètres de configuration de mise à jour des périphériques appliqués à l’étendue du site :
    
        Get-CsDeviceUpdateConfiguration -Filter "site:*" | Remove-CsDeviceUpdateConfiguration

</div>

<div>

## <a name="to-remove-device-update-configuration-settings-based-on-the-value-of-the-logcleanupinterval-property"></a>Pour supprimer les paramètres de configuration de mise à jour des périphériques en fonction de la valeur de la propriété LogCleanUpInterval

  - La commande suivante supprime tous les paramètres de configuration de mise à jour des périphériques dont l’intervalle de nettoyage des journaux est supérieur à 10 jours (10,00:00:00) :
    
        Get-CsDeviceUpdateConfiguration | Where-Object {$_.LogCleanUpInterval -gt "10.00:00:00" | Remove-CsDeviceUpdateConfiguration

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Remove-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

