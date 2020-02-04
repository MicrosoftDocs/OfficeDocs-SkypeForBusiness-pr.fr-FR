---
title: Configuration des certificats et des stratégies d’accès de passerelle XMPP
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure XMPP gateway access policies and certificates
ms:assetid: fac02f4e-d14d-4be3-b53c-74c82436fd93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721945(v=OCS.15)
ms:contentKeyID: 49733882
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b1aab41b1a9af8c7b8df888dcb3a0c8621fa44e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723234"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a>Configuration des certificats et des stratégies d’accès de passerelle XMPP

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-15_

La Fédération XMPP définit un déploiement externe en fonction du protocole XMPP (eXtensible Messaging and Presence Protocol). Une configuration XMPP permet aux utilisateurs de Lync d’accéder aux utilisateurs de domaine XMPP en procédant comme suit :

  - Messagerie instantanée et présence-personne à personne uniquement

  - Créer des contacts fédérés de XMPP dans le client Lync

Lorsque vous configurez des stratégies pour la prise en charge des partenaires fédérés du protocole de messagerie extensible et de présence, les stratégies s’appliquent aux utilisateurs des domaines fédérés de XMPP, mais pas aux utilisateurs de services de messagerie instantanée SIP (Session Initiation Protocol). (par exemple, Windows Live) ou domaines fédérés SIP. Vous configurez un partenaire fédéré de XMPP pour chaque domaine fédéré XMPP que vous voulez autoriser vos utilisateurs à ajouter des contacts et à communiquer avec eux. Une fois les stratégies en place, vous devez configurer les certificats de passerelle XMPP.

<div>


> [!NOTE]  
> Pour lancer la migration de la passerelle XMPP, vous devez déployer la passerelle de Lync Server 2013 XMPP et configurer des stratégies d’accès pour permettre aux utilisateurs de Lync Server 2013 la passerelle XMPP. Pour pouvoir effectuer cette procédure, tous les utilisateurs doivent être déplacés vers le déploiement Lync Server 2013. Pour plus d’informations, consultez <A href="configure-xmpp-gateway-on-lync-server-2013.md">configurer la passerelle XMPP sur Lync Server 2013</A>.



</div>

<div>

## <a name="configure-an-external-access-policy-to-enable-users-for-lync-server-2013-xmpp-gateway"></a>Configurer une stratégie d’accès externe pour permettre aux utilisateurs de Lync Server 2013-passerelle XMPP

1.  Ouvrez le Paneau de configuration Lync Server.

2.  Dans la barre de navigation de gauche, cliquez sur **Fédération et accès externe**, puis sur **stratégie d’accès externe**.

3.  Cliquez sur **nouveau** , puis sur stratégie de l' **utilisateur**.

4.  Entrez le nom de la stratégie de l’utilisateur pour l’accès externe.

5.  Entrez une description pour la stratégie utilisateur d’accès externe.

6.  Sélectionnez **activer les communications avec les utilisateurs fédérés**.

7.  Sélectionnez **activer les communications avec les utilisateurs fédérés de XMPP**.

8.  Cliquez sur **valider** pour enregistrer les modifications apportées à la stratégie de site ou d’utilisateur.

</div>

</div>

<span> </span>

</div>

</div>

</div>

