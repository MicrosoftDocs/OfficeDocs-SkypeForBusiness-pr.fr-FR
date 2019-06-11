---
title: 'Lync Server 2013: supprimer une règle de mise à jour d’appareil'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Remove a Device Update rule
ms:assetid: ad6e0c6a-cda4-4147-92d5-48bc393ac456
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994066(v=OCS.15)
ms:contentKeyID: 51803977
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3776fe2b80e301e02c099f3c6154afc1c382d0d7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823244"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-a-device-update-rule-in-lync-server-2013"></a>Supprimer une règle de mise à jour d’appareil dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-23_

La suppression d’une règle de mise à jour d’appareil permet de supprimer définitivement la file d’attente de mise à jour de l’appareil.

La suppression d’une règle est différente de la désinstallation d’une mise à jour à partir des appareils de votre déploiement ou de vos périphériques de test. Pour désinstaller une mise à jour approuvée de votre ** déploiement, vous restaurez la règle de mise à jour de l’appareil. Pour plus d’informations, reportez-vous à [restaurer une règle de mise à jour d’appareil dans Lync Server 2013](lync-server-2013-restore-a-device-update-rule.md). Pour désinstaller une mise à jour que vous n’avez pas approuvée de vos appareils de test, vous pouvez la *Réinitialiser* . Pour plus d’informations, voir [Réinitialiser une règle de mise à jour d’appareil dans Lync Server 2013](lync-server-2013-reset-a-device-update-rule.md).

Vous pouvez supprimer une règle de mise à jour de l’appareil en utilisant le panneau de configuration de Lync Server ou Windows PowerShell.

<div>

## <a name="to-remove-device-update-rules-by-using-lync-server-control-panel"></a>Pour supprimer les règles de mise à jour des appareils à l’aide du panneau de configuration de Lync Server

1.  À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **clients**, puis sur le bouton de navigation **mise à jour d’appareil** .

4.  Dans la page **mise à jour** de l’appareil, effectuez l’une des opérations suivantes:
    
      - Pour supprimer une règle, sélectionnez la règle que vous voulez supprimer.
    
      - Pour supprimer toutes les règles, cliquez sur le menu **modifier** , puis sur **Sélectionner tout**.

5.  Cliquez sur **Modifier**, puis sur **Supprimer**.

</div>

<div>

## <a name="removing-device-update-rules-by-using-windows-powershell-cmdlets"></a>Suppression des règles de mise à jour des appareils à l’aide des cmdlets Windows PowerShell

Les règles de mise à jour d’appareils peuvent également être supprimées à l’aide de Windows PowerShell et de l’applet de passe **Remove-CsDeviceUpdateRule** . Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell».

<div>

## <a name="to-remove-a-single-device-update-rule-from-a-server"></a>Pour supprimer une seule règle de mise à jour d’un appareil d’un serveur

  - La commande suivante supprime la règle de mise à jour de l’appareil d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 du serveur Web sur atl-cs-001.litwareinc.com.
    
        Remove-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-remove-all-the-device-update-rules-from-a-server"></a>Pour supprimer toutes les règles de mise à jour d’appareil d’un serveur

  - Cette commande supprime toutes les règles de mise à jour de l’appareil du serveur Web sur atl-cs-001.litwareinc.com.
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Remove-CsDeviceUpdateRule

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de connexion [Remove-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateRule) .

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Approuver une règle de mise à jour d’appareil dans Lync Server 2013](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

