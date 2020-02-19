---
title: 'Lync Server 2013 : affichage des informations sur les règles de mise à jour des appareils'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View information about Device Update rules
ms:assetid: d6677ca4-024b-4816-8511-8d7630788107
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994077(v=OCS.15)
ms:contentKeyID: 51803988
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11d43c821c1d1502bed57a8005763a5383777d34
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136732"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-information-about-device-update-rules-in-lync-server-2013"></a>Afficher des informations sur les règles de mise à jour des périphériques dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Afficher les détails sur les règles de mise à jour des périphériques qui ont déjà été importées, y compris le type, le modèle et la marque des périphériques auxquels la mise à jour s’applique ; version et type de mise à jour ; et les paramètres régionaux et pool pour la mise à jour. Les informations sont disponibles pour toutes les règles de mise à jour des appareils importées, celles qui sont en attente d’approbation, déployées (approuvées), rappelées (restaurées) et celles que vous avez décidé de ne pas utiliser (Réinitialiser). Accédez à ces informations à partir du panneau de configuration Lync Server ou de Windows PowerShell.

<div>


> [!NOTE]  
> Pour plus d’informations sur l’importation, l’approbation, la réinitialisation, la restauration et la suppression de règles, voir les rubriques répertoriées <A href="lync-server-2013-device-update-rules.md">dans règles de mise à jour des périphériques dans Lync Server 2013</A>.



</div>

<div>

## <a name="to-view-device-update-rules-by-using-lync-server-control-panel"></a>Pour afficher les règles de mise à jour des périphériques à l’aide du panneau de configuration Lync Server

1.  Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **clients**, puis sur le bouton de navigation **mise à jour des périphériques** . Les règles importées sont répertoriées dans la page **mise à jour du périphérique** .

</div>

<div>

## <a name="viewing-device-update-rules-by-using-windows-powershell-cmdlets"></a>Affichage des règles de mise à jour des périphériques à l’aide des applets de commande Windows PowerShell

Vous pouvez également afficher des informations détaillées sur toutes les règles de mise à jour des appareils à l’aide de Windows PowerShell et de la cmdlet **Get-CsDeviceUpdateRule** . Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell.

<div>


> [!NOTE]  
> Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.



</div>

<div>

## <a name="to-view-all-your-device-update-rules"></a>Pour afficher toutes les règles de mise à jour des appareils

  - La commande suivante retourne des informations sur toutes les règles de mises à jour de périphériques configurées pour être utilisées dans votre organisation :
    
        Get-CsDeviceUpdateRule
    
    La commande retourne des informations semblables aux suivantes pour chacune de vos règles de mise à jour de périphérique :
    
        Identity        : Service:WebServer:pool0.vdomain.com/2de8cbf6-9441-4f61-b755-1e4bef1effde
        Id              : 2de8cbf6-9441-4f61-b755-1e4bef1effde
        DeviceType      : UCPhone
        Brand           : Microsoft
        Model           : CPE
        Revision        : A
        Locale          : ENU
        UpdateType      : CPE
        ApprovedVersion :
        RestoreVersion  :
        PendingVersion  : 4.0.7577.4066

</div>

<div>

## <a name="to-view-all-the-device-update-rules-on-a-specific-web-server"></a>Pour afficher toutes les règles de mise à jour des périphériques sur un serveur Web spécifique

  - Pour afficher les règles de mise à jour des périphériques sur un ordinateur spécifique, utilisez le paramètre Filter suivi de l’identité du serveur\*et du caractère générique (). Par exemple :
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Get-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateRule) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

