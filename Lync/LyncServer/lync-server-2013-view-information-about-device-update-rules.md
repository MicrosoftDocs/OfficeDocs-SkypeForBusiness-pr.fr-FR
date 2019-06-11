---
title: 'Lync Server 2013: afficher des informations sur les règles de mise à jour des appareils'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View information about Device Update rules
ms:assetid: d6677ca4-024b-4816-8511-8d7630788107
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994077(v=OCS.15)
ms:contentKeyID: 51803988
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d873cbd80e599313b60a57cfc28eb9752d85ef66
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846301"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-information-about-device-update-rules-in-lync-server-2013"></a>Afficher des informations sur les règles de mise à jour des appareils dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-23_

Afficher des détails sur les règles de mise à jour d’appareils qui ont déjà été importées, dont le type, le modèle et la marque des appareils auxquels la mise à jour s’applique; version et type de mise à jour; et des paramètres régionaux et du pool pour la mise à jour. Des informations sont disponibles pour toutes les règles de mise à jour d’appareils importées, celles-ci sont en attente d’approbation, de déploiement (approuvé), de rappel (restauration) et de celles que vous avez choisi de ne pas utiliser (Réinitialiser). Accédez à ces informations à partir du panneau de configuration de Lync Server ou de Windows PowerShell.

<div>


> [!NOTE]  
> Pour plus d’informations sur l’importation, l’approbation, la réinitialisation, la restauration et la suppression de règles, voir les rubriques répertoriées dans les <A href="lync-server-2013-device-update-rules.md">règles de mise à jour des appareils de Lync Server 2013</A>.



</div>

<div>

## <a name="to-view-device-update-rules-by-using-lync-server-control-panel"></a>Pour afficher les règles de mise à jour de l’appareil à l’aide du panneau de configuration de Lync Server

1.  À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **clients**, puis sur le bouton de navigation **mise à jour d’appareil** . Les règles importées sont répertoriées dans la page de **mise à jour** de l’appareil.

</div>

<div>

## <a name="viewing-device-update-rules-by-using-windows-powershell-cmdlets"></a>Affichage des règles de mise à jour des appareils à l’aide des cmdlets Windows PowerShell

Vous pouvez également afficher des informations détaillées sur toutes les règles de mise à jour de l’appareil à l’aide de Windows PowerShell et de l’applet **de passe Get-CsDeviceUpdateRule** . Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell.

<div>


> [!NOTE]  
> Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync <A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>Server 2010 à l’aide de Remote PowerShell».



</div>

<div>

## <a name="to-view-all-your-device-update-rules"></a>Pour afficher toutes les règles de mise à jour de l’appareil

  - La commande suivante renvoie des informations sur toutes les règles de mise à jour de l’appareil configurées pour une utilisation au sein de votre organisation:
    
        Get-CsDeviceUpdateRule
    
    La commande renvoie des informations similaires à ce qui suit pour chacune de vos règles de mise à jour de l’appareil:
    
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

## <a name="to-view-all-the-device-update-rules-on-a-specific-web-server"></a>Pour afficher toutes les règles de mise à jour de l’appareil sur un serveur Web spécifique

  - Pour afficher les règles de mise à jour de l’appareil sur un ordinateur spécifique, utilisez le paramètre de filtre suivi de l’identité\*du serveur et du caractère générique (). Par exemple :
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de connexion [Get-CsDeviceUpdateRule](https://docs.microsoft.com/powershell/module/skype/Get-CsDeviceUpdateRule) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

