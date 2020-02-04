---
title: 'Lync Server 2013 : supprimer une collection de paramètres de configuration de la mise à jour de l’appareil'
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
ms.openlocfilehash: 936a591ea46c6b599a9a72f06a9287be35e66cce
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728194"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-a-collection-of-device-update-configuration-settings-in-lync-server-2013"></a>Supprimer un ensemble de paramètres de configuration de la mise à jour de périphériques dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-20_

Les paramètres de configuration de la mise à jour de l’appareil peuvent également être supprimés à l’aide de Windows PowerShell et de l’applet de passe **Remove-CsdeviceUpdateConfiguration** . Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell ».

<div>


<div>

## <a name="to-remove-a-specific-collection-of-device-update-configuration-settings"></a>Pour supprimer une collection spécifique de paramètres de configuration de la mise à jour de l’appareil

  - Cette commande supprime les paramètres de configuration de la mise à jour de l’appareil appliqués au site de Redmond :
    
        Remove-CsDeviceUpdateConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-the-device-update-configuration-settings-applied-to-the-site-scope"></a>Pour supprimer tous les paramètres de configuration de la mise à jour de l’appareil appliqués à l’étendue du site

  - Cette commande supprime tous les paramètres de configuration de la mise à jour de l’appareil appliqués à l’étendue du site :
    
        Get-CsDeviceUpdateConfiguration -Filter "site:*" | Remove-CsDeviceUpdateConfiguration

</div>

<div>

## <a name="to-remove-device-update-configuration-settings-based-on-the-value-of-the-logcleanupinterval-property"></a>Pour supprimer les paramètres de configuration de la mise à jour de périphériques en fonction de la valeur de la propriété LogCleanUpInterval

  - La commande suivante supprime tous les paramètres de configuration de la mise à jour de l’appareil, où l’intervalle de nettoyage du journal est supérieur à 10 jours (10,00:00:00) :
    
        Get-CsDeviceUpdateConfiguration | Where-Object {$_.LogCleanUpInterval -gt "10.00:00:00" | Remove-CsDeviceUpdateConfiguration

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de connexion [Remove-CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateConfiguration) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

