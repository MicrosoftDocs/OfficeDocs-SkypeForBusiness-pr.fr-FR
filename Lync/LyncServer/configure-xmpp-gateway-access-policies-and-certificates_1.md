---
title: Configuration des certificats et des stratégies d’accès de passerelle XMPP
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure XMPP gateway access policies and certificates
ms:assetid: cd91433e-6dfb-4553-8316-c1086b394221
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721885(v=OCS.15)
ms:contentKeyID: 49733819
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72e17634a8836a56ce7002e3d0cf57440f72c60f
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754462"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a>Configuration des certificats et des stratégies d’accès de passerelle XMPP

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-15_

XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP). An XMPP configuration allows Lync users access to XMPP domain users by:

  - la messagerie instantanée et la présence (personne à personne uniquement) ;

  - la création de contacts fédérés XMPP dans le client Lync.

When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains. You configure an XMPP Federated Partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with. Once the policies are in place, you need to configure the XMPP Gateway certificates.

<div>


> [!NOTE]  
> Pour commencer la migration de la passerelle XMPP, vous devez déployer la passerelle XMPP Lync Server 2013 et configurer des stratégies d’accès pour activer les utilisateurs pour la passerelle XMPP Lync Server 2013. Tous les utilisateurs doivent être déplacés vers le déploiement Lync Server 2013 avant d’effectuer ces étapes. Pour plus d’informations, reportez-vous à la rubrique <A href="configure-xmpp-gateway-on-lync-server-2013_1.md">configurer la passerelle XMPP sur Lync Server 2013</A>.



</div>

<div>

## <a name="configure-an-external-access-policy-to-enable-users-for-lync-server-2013-xmpp-gateway"></a>Pour configurer une stratégie d’accès externe et activer les utilisateurs pour la passerelle XMPP Lync Server 2013

1.  Ouvrez le Panneau de configuration Lync Server.

2.  Dans la barre de navigation de gauche, cliquez sur **Fédération et accès externe**, puis sur **Stratégie d’accès externe**.

3.  Cliquez sur **Nouvelle**, puis sur **Stratégie utilisateur**.

4.  Entrez un nom pour la stratégie utilisateur d’accès externe.

5.  Fournissez une description pour la stratégie utilisateur d’accès externe.

6.  Sélectionnez **Activer les communications avec les utilisateurs fédérés**.

7.  Sélectionnez **Activer les communications avec les utilisateurs fédérés XMPP**.

8.  Cliquez sur **Valider** pour enregistrer les modifications apportées à la stratégie de site ou utilisateur.

</div>

</div>

<span> </span>

</div>

</div>

</div>

