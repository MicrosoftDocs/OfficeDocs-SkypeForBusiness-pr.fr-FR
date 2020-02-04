---
title: 'Lync Server 2013 : réinitialiser une règle de mise à jour d’appareil'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reset a Device Update rule
ms:assetid: d1f597e7-dffd-4756-af07-10613a5d8729
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994069(v=OCS.15)
ms:contentKeyID: 51803980
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36a85ed29f6bf4838428af302904d80a2f792388
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723764"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reset-a-device-update-rule-in-lync-server-2013"></a>Réinitialiser une règle de mise à jour d’appareil dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Si vous ne voulez pas que la mise à jour fonctionne sur vos appareils de test, vous pouvez réinitialiser la règle de mise à jour de l’appareil, qui supprime l’État en attente de la règle et désinstaller la mise à jour des périphériques de test.

Vous pouvez supprimer une règle de mise à jour de l’appareil en utilisant le panneau de configuration de Lync Server ou Windows PowerShell.

<div>


> [!NOTE]  
> Pour désinstaller une règle que vous avez déjà approuvée (qui est déployée), restaurez-la. Pour plus d’informations, reportez-vous à <A href="lync-server-2013-restore-a-device-update-rule.md">restaurer une règle de mise à jour d’appareil dans Lync Server 2013</A>.



</div>

<div>

## <a name="to-reset-a-device-update-rule-by-using-lync-server-control-panel"></a>Pour réinitialiser une règle de mise à jour de l’appareil à l’aide du panneau de configuration de Lync Server

1.  À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **clients**, puis sur le bouton de navigation **mise à jour d’appareil** .

4.  Dans la page **mise à jour** de l’appareil, effectuez l’une des opérations suivantes :
    
      - Pour réinitialiser une règle, sélectionnez la règle que vous voulez réinitialiser.
    
      - Pour réinitialiser toutes les règles, dans le menu **édition** , cliquez sur **Sélectionner tout**.
    
      - Pour réinitialiser toutes les règles pour une seule marque, utilisez le menu de la colonne de **marque** .

5.  Cliquez sur **action**, puis sur **annuler les mises à jour en attente**.
    
    <div>
    

    > [!TIP]  
    > Si vous êtes sûr de ne jamais vouloir déployer les règles de mise à jour de l’appareil que vous avez annulées, vous souhaiterez peut-être les supprimer. Pour plus d’informations, reportez-vous à <A href="lync-server-2013-remove-a-device-update-rule.md">supprimer une règle de mise à jour d’appareil dans Lync Server 2013</A>.

    
    </div>

</div>

<div>

## <a name="resetting-a-device-update-rule-by-using-windows-powershell-cmdlets"></a>Réinitialisation d’une règle de mise à jour de l’appareil à l’aide des cmdlets Windows PowerShell

Les règles de mise à jour d’appareils peuvent également être réinitialisées à l’aide de Windows PowerShell et de l’applet de passe **Reset-CsDeviceUpdateRule** . Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell.

<div>


> [!NOTE]  
> Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Server 2010 à l’aide de Remote PowerShell ».



</div>

<div>

## <a name="to-reset-a-specific-device-update-rule-on-a-server"></a>Pour réinitialiser une règle de mise à jour de l’appareil spécifique sur un serveur

  - La commande suivante réinitialise la règle de mise à jour de l’appareil d5ce3c10-2588-420a-82ac-dc2d9b1222ff9 sur le serveur Web atl-cs-001.litwareinc.com :
    
        Reset-CsDeviceUpdateRule -Identity "service:WebServer:atl-cs-001.litwareinc.com/d5ce3c10-2588-420a-82ac-dc2d9b1222ff9"

</div>

<div>

## <a name="to-reset-all-the-device-update-rules-on-a-server"></a>Pour réinitialiser toutes les règles de mise à jour de l’appareil sur un serveur

  - Cette commande réinitialise toutes les règles de mise à jour de l’appareil sur le serveur Web atl-cs-001.litwareinc.com :
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"  | Reset-CsDeviceUpdateRule

</div>

<div>

## <a name="to-reset-all-the-device-updates-rules-that-have-a-specific-brand"></a>Pour réinitialiser toutes les règles de mises à jour de périphériques ayant une marque spécifique

  - Dans cet exemple, toutes les mises à jour de l’appareil dans l’ensemble de l’organisation dont la marque est égale à Microsoft sont réinitialisées :
    
        Get-CsDeviceUpdateRule | Where-Object {$_.Brand -eq "Microsoft"} | Reset-CsDeviceUpdateRule

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de connexion [Reset-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Reset-CsDeviceUpdateRule) .

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

