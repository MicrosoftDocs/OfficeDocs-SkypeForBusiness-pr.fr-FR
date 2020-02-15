---
title: 'Lync Server 2013 : restaurer une règle de mise à jour de périphérique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restore a Device Update rule
ms:assetid: ac490baf-c7a0-48d9-8fd0-ba5729489341
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994061(v=OCS.15)
ms:contentKeyID: 51803972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 728adc1384738d93fc7ac4506a55621830c7de39
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051286"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restore-a-device-update-rule-in-lync-server-2013"></a>Restaurer une règle de mise à jour de périphérique dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Pour désinstaller une règle de mise à jour de périphérique à partir des appareils de votre déploiement, restaurez-la. La restauration d’une règle de mise à jour de périphérique désinstalle la mise à jour et réinstalle la version précédente de cette règle.

Vous pouvez restaurer une règle de mise à jour des périphériques à l’aide du panneau de configuration Lync Server ou de Windows PowerShell.

<div>

## <a name="to-restore-device-update-rules-by-using-lync-server-control-panel"></a>Pour restaurer des règles de mise à jour des périphériques à l’aide du panneau de configuration Lync Server

1.  Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **clients**, puis sur le bouton de navigation **mise à jour des périphériques** .

4.  Sur la page **mise à jour du périphérique** , effectuez l’une des opérations suivantes :
    
      - Pour restaurer une règle, sélectionnez cette règle.
    
      - Pour restaurer toutes les règles, cliquez sur **modifier**, puis cliquez sur **Sélectionner tout**.

5.  Cliquez sur le menu **action** , puis sur **restaurer**.

</div>

<div>

## <a name="restoring-device-update-rules-by-using-windows-powershell-cmdlets"></a>Restauration des règles de mise à jour des périphériques à l’aide des applets de commande Windows PowerShell

Les règles de mise à jour des appareils peuvent également être restaurées à l’aide de Windows PowerShell et de la cmdlet **Restore-CsDeviceUpdateRule** .. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.

<div>


> [!NOTE]  
> Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.



</div>

<div>

## <a name="to-restore-a-single-device-update-rule-on-a-server"></a>Pour restaurer une règle de mise à jour de périphérique unique sur un serveur

  - La commande suivante restaure la règle de mise à jour de périphérique d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 sur le serveur Web atl-cs-001.litwareinc.com :
    
        Restore-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-restore-all-the-device-update-rules-on-a-server"></a>Pour restaurer toutes les règles de mise à jour des périphériques sur un serveur

  - Cette commande restaure toutes les règles de mise à jour des périphériques sur le serveur Web atl-cs-001.litwareinc.com :
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Restore-CsDeviceUpdateRule

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à la cmdlet [Restore-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Restore-CsDeviceUpdateRule) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

