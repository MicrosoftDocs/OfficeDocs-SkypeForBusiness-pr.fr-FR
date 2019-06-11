---
title: 'Lync Server 2013: restaurer une règle de mise à jour d’appareil'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restore a Device Update rule
ms:assetid: ac490baf-c7a0-48d9-8fd0-ba5729489341
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994061(v=OCS.15)
ms:contentKeyID: 51803972
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 90eeb82e710b6ea65bc32184685497494dbef8d6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823090"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restore-a-device-update-rule-in-lync-server-2013"></a>Restaurer une règle de mise à jour d’appareil dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-23_

Pour désinstaller une règle de mise à jour de l’appareil des appareils de votre déploiement, restaurez-la. La restauration d’une règle de mise à jour de l’appareil à la fois désinstalle la mise à jour et réinstalle la version précédente de cette règle.

Vous pouvez restaurer une règle de mise à jour de l’appareil à l’aide du panneau de configuration de Lync Server ou de Windows PowerShell.

<div>

## <a name="to-restore-device-update-rules-by-using-lync-server-control-panel"></a>Pour restaurer les règles de mise à jour de l’appareil à l’aide du panneau de configuration de Lync Server

1.  À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **clients**, puis sur le bouton de navigation **mise à jour d’appareil** .

4.  Dans la page **mise à jour** de l’appareil, effectuez l’une des opérations suivantes:
    
      - Pour restaurer une règle, sélectionnez cette règle.
    
      - Pour restaurer toutes les règles, cliquez sur **modifier**, puis sur **Sélectionner tout**.

5.  Cliquez sur le menu **action** , puis cliquez sur **restaurer**.

</div>

<div>

## <a name="restoring-device-update-rules-by-using-windows-powershell-cmdlets"></a>Restauration de règles de mise à jour de l’appareil à l’aide des cmdlets Windows PowerShell

Les règles de mises à jour de périphériques peuvent également être restaurées à l’aide de Windows PowerShell et de l’applet de passe **Restore-CsDeviceUpdateRule** . Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell.

<div>


> [!NOTE]  
> Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Server 2010 à l’aide de Remote PowerShell».



</div>

<div>

## <a name="to-restore-a-single-device-update-rule-on-a-server"></a>Pour restaurer une seule règle de mise à jour d’un appareil sur un serveur

  - La commande suivante restaure la règle de mise à jour d’appareil d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 sur le serveur Web atl-cs-001.litwareinc.com:
    
        Restore-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-restore-all-the-device-update-rules-on-a-server"></a>Pour restaurer toutes les règles de mise à jour de l’appareil sur un serveur

  - Cette commande restaure toutes les règles de mise à jour de l’appareil sur le serveur Web atl-cs-001.litwareinc.com:
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Restore-CsDeviceUpdateRule

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de connexion [Restore-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Restore-CsDeviceUpdateRule) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

