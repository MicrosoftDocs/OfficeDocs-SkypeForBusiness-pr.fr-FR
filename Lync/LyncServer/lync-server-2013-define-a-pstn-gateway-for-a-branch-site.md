---
title: 'Lync Server 2013 : définition d’une passerelle PSTN pour un site de succursale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a PSTN gateway for a branch site
ms:assetid: 87be2fe2-1d56-4062-b430-439d4536414c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398689(v=OCS.15)
ms:contentKeyID: 48184724
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 435af3ab537097592325438707b89ce901da9bcd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516391"
---
# <a name="define-a-pstn-gateway-for-a-branch-site-in-lync-server-2013"></a>Définition d’une passerelle PSTN pour un site de succursale dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-21_

Effectuez cette procédure sur le site central, qui contient au moins un pool frontal ou un serveur Standard Edition.

<div>


> [!IMPORTANT]  
> Avant d’effectuer la procédure, les conditions suivantes doivent être remplies : 
> <UL>
> <LI>
> <P>&nbsp;Les logiciels de communication Lync Server 2013 doivent être configurés sur le site central.</P>
> <LI>
> <P>Le serveur de médiation doit être déployé sur le site central.</P></LI></UL>



</div>

<div>

## <a name="to-define-a-pstn-gateway"></a>Pour définir une passerelle PSTN

1.  Cliquez sur **Démarrer**, **Tous les programmes**, **Microsoft Lync Server**, puis sur **Générateur de topologie Lync Server**.

2.  Dans l’arborescence de la console, développez le site central, développez **Sites de succursale**, développez le nom du site de succursale pour lequel définir une passerelle PSTN, puis développez **Composants partagés**..

3.  Cliquez avec le bouton droit sur **Passerelles PSTN**, puis cliquez sur **Nouvelle passerelle IP/PSTN**.

4.  Dans la boîte de dialogue **Définir une nouvelle passerelle IP/PSTN**, cliquez sur **Passerelle FQDN ou adresse IP**, puis tapez le nom de domaine complet ou l’adresse IP de la passerelle que vous souhaitez déployer sur le site de succursale.

5.  Cliquez sur **Port d’écoute pour la passerelle IP/PSTN**, puis acceptez les valeurs par défaut.

6.  Dans la liste **Protocole de transport SIP**, cliquez sur le protocole de transport utilisé par la passerelle, puis cliquez sur **OK**.
    
    <div>
    

    > [!NOTE]  
    > Pour des raisons de sécurité, nous vous conseillons vivement d’utiliser une passerelle PSTN qui prend en charge le protocole TLS (Transport Layer Security).

    
    </div>

<div>


> [!TIP]  
> Utilisez l’applet de commande  <STRONG>Set-CsPstnGateway</STRONG> pour modifier les propriétés d’une passerelle PSTN. Pour plus d’informations, reportez-vous à <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsPstnGateway">Set-applet cspstngateway</A>dans l’aide de Lync Server Management Shell.



</div>

**Étape suivante** pour la résistance des sites de succursale : [Configuration des utilisateurs pour la résistance des sites de succursale dans Lync Server 2013](lync-server-2013-configuring-users-for-branch-site-resiliency.md)

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Options de déploiement de passerelle PSTN dans Lync Server 2013](lync-server-2013-pstn-gateway-deployment-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

