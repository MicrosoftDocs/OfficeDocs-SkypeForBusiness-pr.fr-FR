---
title: 'Lync Server 2013: configuration d’une voie vocale E9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure an E9-1-1 voice route
ms:assetid: 6933b840-0e7b-4509-ae43-bc9065677547
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398496(v=OCS.15)
ms:contentKeyID: 48184384
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59f4e2a6707d270f66a66663b19f975ac69961c2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838440"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-an-e9-1-1-voice-route-in-lync-server-2013"></a>Configurer un itinéraire vocal E9-1-1 dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-17_

Pour déployer E9-1-1, vous devez d’abord configurer un itinéraire des communications vocales pour les appels d’urgence. Pour plus d’informations sur la création d’itinéraires vocaux, voir [créer un itinéraire vocal dans Lync Server 2013](lync-server-2013-create-a-voice-route.md). Vous pouvez définir plusieurs itinéraires si, par exemple, votre déploiement comporte une jonction SIP (Session Initiation Protocol) principale et une jonction SIP secondaire.

<div>


> [!NOTE]  
> Pour inclure des informations d’emplacement dans une invitation E9-1-1, vous devez configurer le Trunk SIP qui se connecte au fournisseur de services E9-1-1 pour diriger les appels d’urgence par le biais de la passerelle. Pour ce faire, définissez l’indicateur EnablePIDFLOSupport sur la cmdlet <STRONG>Set-CsTrunkConfiguration</STRONG> sur true. La valeur par défaut de EnablePIDFLOSupport est false. Par exemple:<CODE>Set-CsTrunkConfiguration Service:PstnGateway:192.168.0.241 -EnablePIDFLOSupport $true.</CODE><BR>Il n’est pas nécessaire d’activer la réception des emplacements pour les passerelles du réseau téléphonique commuté (RTC) et les passerelles ELIN (Emergency Location Identification Number).



</div>

Pour plus d’informations sur l’utilisation des itinéraires vocaux, voir la documentation Lync Server Management Shell pour les applets de commande suivantes:

  - **Set-CsPstnUsage**

  - **Get-CsPstnUsage**

  - **Nouveau-CsVoiceRoute**

  - **Get-CsVoiceRoute**

  - **Set-CsVoiceRoute**

  - **Remove-CsVoiceRoute**

<div>

## <a name="to-configure-an-e9-1-1-voice-route"></a>Pour configurer un itinéraire des communications vocales E9-1-1

1.  Ouvrez une session sur l’ordinateur à l’aide d’un compte membre du groupe RTCUniversalServerAdmins ou du rôle d’administration CsVoiceAdministrator.

2.  Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Exécutez l’applet de commande ci-dessous pour créer un enregistrement d’utilisation RTC.
    
    Ce nom doit être identique à celui que vous utiliserez pour le paramètre **RTC** de la stratégie d’emplacement. Si votre déploiement comporte plusieurs enregistrements d’utilisation téléphonique, l’exemple ci-dessous ajoute « Emergency Usage » (Utilisation d’urgence) à la liste actuelle des utilisations RTC disponibles. Pour plus d’informations, reportez-vous [à configuration des stratégies de voix et des enregistrements d’utilisation RTC pour autoriser les fonctionnalités et privilèges d’utilisation dans Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).
    
        Set-CsPstnUsage -Usage @{add='EmergencyUsage'}

4.  Exécutez l’applet de commande ci-dessous pour créer un itinéraire des communications vocales à l’aide de l’enregistrement d’utilisation RTC créé lors de l’étape précédente.
    
    Le modèle de numéro doit être identique à celui utilisé dans le paramètre **Chaîne de numérotation d’urgence** de la stratégie d’emplacement. Le signe "+" est nécessaire car Lync ajoute "+" aux appels d’urgence. « Co1-pstngateway-1 » est l’ID du service de jonction SIP (Session Initiation Protocol) pour le fournisseur de services E9-1-1 ou l’ID du service de passerelle ELIN. L’exemple ci-dessous utilise « EmergencyRoute » comme nom de l’itinéraire des communications vocales.
    
        New-CsVoiceRoute -Name "EmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="EmergencyUsage"} -PstnGatewayList @{add="co1-pstngateway-1"}

5.  Pour les connexions à une jonction SIP (Session Initiation Protocol), nous vous conseillons éventuellement d’exécuter l’applet de commande ci-dessous pour créer un itinéraire local pour les appels qui ne sont pas gérés par la jonction SIP du fournisseur de services E9-1-1. Cet itinéraire est utilisé si la connexion au fournisseur de services E9-1-1 n’est pas disponible.
    
    L’exemple ci-dessous part du principe que l’utilisateur a une utilisation « locale » dans sa stratégie de voix.
    
        New-CsVoiceRoute -Name "LocalEmergencyRoute" -NumberPattern "^\+911$" -PstnUsages @{add="Local"} -PstnGatewayList @{add="co1-pstngateway-2"}

</div>

</div>

<span> </span>

</div>

</div>

</div>

