---
title: 'Lync Server 2013 : suppression d’une règle de mise à jour de périphérique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Remove a Device Update rule
ms:assetid: ad6e0c6a-cda4-4147-92d5-48bc393ac456
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994066(v=OCS.15)
ms:contentKeyID: 51803977
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f89e932dbbbde0adbd972eb3bfd5c79e9026be0c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536541"
---
# <a name="remove-a-device-update-rule-in-lync-server-2013"></a>Supprimer une règle de mise à jour de périphérique dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

La suppression d’une règle de mise à jour de périphérique supprime définitivement la file d’attente de mise à jour des périphériques.

La suppression d’une règle est différente de la désinstallation d’une mise à jour des appareils de votre déploiement ou de vos périphériques de test. Pour désinstaller une mise à jour approuvée de votre déploiement, vous devez *restaurer* la règle de mise à jour des périphériques. Pour plus d’informations, consultez [la rubrique restaurer une règle de mise à jour des périphériques dans Lync Server 2013](lync-server-2013-restore-a-device-update-rule.md). Pour désinstaller une mise à jour que vous n’avez pas approuvée de vos périphériques de test, vous devez la *Réinitialiser* . Pour plus d’informations, voir [Réinitialiser une règle de mise à jour de périphérique dans Lync Server 2013](lync-server-2013-reset-a-device-update-rule.md).

Vous pouvez supprimer une règle de mise à jour de périphérique à l’aide du panneau de configuration Lync Server ou de Windows PowerShell.

<div>

## <a name="to-remove-device-update-rules-by-using-lync-server-control-panel"></a>Pour supprimer des règles de mise à jour des périphériques à l’aide du panneau de configuration Lync Server

1.  Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **clients**, puis sur le bouton de navigation **mise à jour des périphériques** .

4.  Sur la page **mise à jour du périphérique** , effectuez l’une des opérations suivantes :
    
      - Pour supprimer une règle, sélectionnez la règle que vous souhaitez supprimer.
    
      - Pour supprimer toutes les règles, cliquez sur le menu **Edition** , puis cliquez sur **Sélectionner tout**.

5.  Cliquez sur **Modifier**, puis sur **Supprimer**.

</div>

<div>

## <a name="removing-device-update-rules-by-using-windows-powershell-cmdlets"></a>Suppression des règles de mise à jour des périphériques à l’aide des applets de commande Windows PowerShell

Les règles de mise à jour des périphériques peuvent également être supprimées à l’aide de Windows PowerShell et de l’applet de commande **Remove-CsDeviceUpdateRule** . Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-remove-a-single-device-update-rule-from-a-server"></a>Pour supprimer une seule règle de mise à jour de périphérique d’un serveur

  - La commande suivante supprime la règle de mise à jour de périphérique d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 du serveur Web sur atl-cs-001.litwareinc.com.
    
        Remove-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-remove-all-the-device-update-rules-from-a-server"></a>Pour supprimer toutes les règles de mise à jour des périphériques d’un serveur

  - Cette commande supprime toutes les règles de mise à jour des périphériques du serveur Web sur atl-cs-001.litwareinc.com.
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*" | Remove-CsDeviceUpdateRule

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Remove-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Remove-CsDeviceUpdateRule) .

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Approuver une règle de mise à jour de périphérique dans Lync Server 2013](lync-server-2013-approve-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

