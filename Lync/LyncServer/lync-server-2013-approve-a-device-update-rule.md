---
title: 'Lync Server 2013 : approuver une règle de mise à jour de périphérique'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Approve a Device Update rule
ms:assetid: 9dbb1c9a-be0f-4e13-9234-05501ab43ac5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994053(v=OCS.15)
ms:contentKeyID: 51803964
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6537af434a704b23553c217bde3370d49e318f37
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029325"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="approve-a-device-update-rule-in-lync-server-2013"></a>Approuver une règle de mise à jour de périphérique dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Une fois que vous avez importé une règle de mise à jour de périphérique, celle-ci est installée sur vos périphériques de test. Si le test réussit et que vous souhaitez déployer la mise à jour pour votre organisation, approuvez-le à l’aide du panneau de configuration Lync Server ou de Windows PowerShell.

<div>

## <a name="to-approve-a-device-update-rule-by-using-lync-server-control-panel"></a>Pour approuver une règle de mise à jour de périphérique à l’aide du panneau de configuration Lync Server

1.  Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sur la page **mise à jour du périphérique** , effectuez l’une des opérations suivantes :
    
      - Pour approuver une règle, sélectionnez cette règle.
    
      - Pour approuver toutes les règles, cliquez sur **modifier**, puis cliquez sur **Sélectionner tout**.

4.  Cliquez sur **action**, puis sur **approuver**.

</div>

<div>

## <a name="approving-a-device-update-rule-by-using-windows-powershell-cmdlets"></a>Approbation d’une règle de mise à jour de périphérique à l’aide des applets de commande Windows PowerShell

Les règles de mise à jour des périphériques peuvent également être approuvées à l’aide de Windows PowerShell et de la cmdlet **Approve-CsDeviceUpdateRule** . Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.

<div>


> [!NOTE]  
> Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.



</div>

<div>

## <a name="to-approve-a-single-device-update-rule"></a>Pour approuver une règle de mise à jour de périphérique unique

  - La commande suivante approuve la règle de mise à jour de périphérique d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 trouvée sur le serveur Web atl-cs-001.litwareinc.com :
    
        Approve-CsDeviceUpdateRule -Identity service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9

</div>

<div>

## <a name="to-approve-multiple-device-update-rules"></a>Pour approuver plusieurs règles de mise à jour des périphériques

  - Cette commande approuve toutes les règles de mise à jour des appareils pour les périphériques de marque Microsoft :
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Approve-CsDeviceUpdateRule

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à la cmdlet [Approve-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Approve-CsDeviceUpdateRule) .

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Importer des règles de mise à jour des périphériques dans Lync Server 2013](lync-server-2013-import-device-update-rules.md)  
[Restaurer une règle de mise à jour de périphérique dans Lync Server 2013](lync-server-2013-restore-a-device-update-rule.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

