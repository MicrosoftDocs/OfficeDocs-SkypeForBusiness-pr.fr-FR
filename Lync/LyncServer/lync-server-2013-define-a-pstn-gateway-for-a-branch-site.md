---
title: 'Lync Server 2013 : Définition d’une passerelle RTC pour un site de succursale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define a PSTN gateway for a branch site
ms:assetid: 87be2fe2-1d56-4062-b430-439d4536414c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398689(v=OCS.15)
ms:contentKeyID: 48184724
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c253f82001fef4dd52e19dccb11e7ac77bb12417
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831717"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-pstn-gateway-for-a-branch-site-in-lync-server-2013"></a>Définition d’une passerelle RTC pour un site de succursale dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-21_

Procédez comme suit sur le site central, qui contient au moins un pool frontal ou un serveur Standard Edition Server.

<div>


> [!IMPORTANT]  
> Avant d’effectuer cette procédure, les conditions suivantes doivent être en vigueur: 
> <UL>
> <LI>
> <P>Le logiciel de&nbsp;communications Lync Server 2013 doit être configuré sur le site central.</P>
> <LI>
> <P>Le serveur de médiation doit être déployé sur le site central.</P></LI></UL>



</div>

<div>

## <a name="to-define-a-pstn-gateway"></a>Pour définir une passerelle RTC

1.  Cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server**, puis sur **Générateur de topologie de Lync Server**.

2.  Dans l’arborescence de la console, développez le site central, développez **sites**de succursales, développez le nom du site de succursale pour lequel vous voulez définir une passerelle de réseau téléphonique commuté (RTC), puis développez **composants partagés**.

3.  Cliquez avec le bouton droit sur **passerelles RTC**, puis cliquez sur **nouvelle passerelle IP/PSTN**.

4.  Dans la boîte de dialogue **définir une nouvelle passerelle IP/PSTN** , cliquez sur **FQDN ou adresse IP de passerelle**, puis tapez le nom de domaine complet (FQDN) ou l’adresse IP de la passerelle que vous déployez sur le site de succursale.

5.  Cliquez sur **port d’écoute pour la passerelle RTC/IP**, puis acceptez les valeurs par défaut.

6.  Dans la liste **protocole de transport SIP** , cliquez sur le protocole de transport utilisé par la passerelle, puis cliquez sur **OK**.
    
    <div>
    

    > [!NOTE]  
    > Pour des raisons de sécurité, nous vous recommandons vivement d’utiliser une passerelle RTC qui prend en charge le protocole TLS (Transport Layer Security).

    
    </div>

<div>


> [!TIP]  
> Utilisez l’applet de cmdlet <STRONG>Set-CsPstnGateway</STRONG> pour modifier les propriétés d’une passerelle PSTN. Pour plus d’informations, reportez-vous à la rubrique <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsPstnGateway">Set-CsPstnGateway</A>dans l’aide de Lync Server Management Shell.



</div>

**Étape suivante** pour la résilience du site de succursale: [Configuration des utilisateurs pour la résilience du site de succursale dans Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Options de déploiement de passerelle RTC dans Lync Server 2013](lync-server-2013-pstn-gateway-deployment-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

