---
title: Configuration des certificats et des stratégies d’accès de passerelle XMPP
description: Configurez les certificats et stratégies d’accès à la passerelle XMPP.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
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
ms.openlocfilehash: e958100501ad9ca87d1ab970162f4be8c7692a99
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549710"
---
# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a><span data-ttu-id="ec1fc-103">Configuration des certificats et des stratégies d’accès de passerelle XMPP</span><span class="sxs-lookup"><span data-stu-id="ec1fc-103">Configure XMPP gateway access policies and certificates</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ec1fc-104">_**Dernière modification de la rubrique :** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="ec1fc-104">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="ec1fc-p101">La fédération XMPP définit un déploiement externe basé sur le protocole XMPP (eXtensible Messaging and Presence Protocol). Une configuration XMPP permet aux utilisateurs de Lync d’accéder aux utilisateurs de domaine XMPP via :</span><span class="sxs-lookup"><span data-stu-id="ec1fc-p101">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP). An XMPP configuration allows Lync users access to XMPP domain users by:</span></span>

  - <span data-ttu-id="ec1fc-107">la messagerie instantanée et la présence (personne à personne uniquement) ;</span><span class="sxs-lookup"><span data-stu-id="ec1fc-107">IM and Presence – person to person only</span></span>

  - <span data-ttu-id="ec1fc-108">la création de contacts fédérés XMPP dans le client Lync.</span><span class="sxs-lookup"><span data-stu-id="ec1fc-108">Creation of XMPP federated contacts in the Lync client</span></span>

<span data-ttu-id="ec1fc-p102">Lorsque vous configurez des stratégies pour la prise en charge des partenaires fédérés XMPP (eXtensible Messaging and Presence Protocol), celles-ci s’appliquent aux utilisateurs de domaines fédérés XMPP, mais pas aux utilisateurs de fournisseurs de services de messagerie instantanée SIP (Session Initiation Protocol) (par exemple, Windows Live), ou aux domaines fédérés SIP. Vous configurez un partenaire fédéré XMPP pour chaque domaine fédéré XMPP souhaité pour permettre aux utilisateurs d’ajouter des contacts et de communiquer avec. Une fois les stratégies en place, vous devez configurer les certificats de passerelle XMPP.</span><span class="sxs-lookup"><span data-stu-id="ec1fc-p102">When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains. You configure an XMPP Federated Partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with. Once the policies are in place, you need to configure the XMPP Gateway certificates.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ec1fc-112">Pour commencer la migration de la passerelle XMPP, vous devez déployer la passerelle XMPP Lync Server 2013 et configurer des stratégies d’accès pour activer les utilisateurs pour la passerelle XMPP Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ec1fc-112">To begin the XMPP Gateway migration, you need to deploy the Lync Server 2013 XMPP Gateway, and configure access policies to enable users for Lync Server 2013 XMPP Gateway.</span></span> <span data-ttu-id="ec1fc-113">Tous les utilisateurs doivent être déplacés vers le déploiement Lync Server 2013 avant d’effectuer ces étapes.</span><span class="sxs-lookup"><span data-stu-id="ec1fc-113">All users must be moved to the Lync Server 2013 deployment before you perform these steps.</span></span> <span data-ttu-id="ec1fc-114">Pour plus d’informations, reportez-vous à la rubrique <A href="configure-xmpp-gateway-on-lync-server-2013.md">configurer la passerelle XMPP sur Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="ec1fc-114">For details, see <A href="configure-xmpp-gateway-on-lync-server-2013.md">Configure XMPP gateway on Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="configure-an-external-access-policy-to-enable-users-for-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="ec1fc-115">Pour configurer une stratégie d’accès externe et activer les utilisateurs pour la passerelle XMPP Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ec1fc-115">Configure an External Access Policy to Enable Users for Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="ec1fc-116">Ouvrez le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ec1fc-116">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="ec1fc-117">Dans la barre de navigation de gauche, cliquez sur **Fédération et accès externe**, puis sur **Stratégie d’accès externe**.</span><span class="sxs-lookup"><span data-stu-id="ec1fc-117">In the left navigation bar, click **Federation and External Access**, and then click **External Access Policy**.</span></span>

3.  <span data-ttu-id="ec1fc-118">Cliquez sur **Nouvelle**, puis sur **Stratégie utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="ec1fc-118">Click **New** and then click **User policy**.</span></span>

4.  <span data-ttu-id="ec1fc-119">Entrez un nom pour la stratégie utilisateur d’accès externe.</span><span class="sxs-lookup"><span data-stu-id="ec1fc-119">Enter a name for the external access user policy.</span></span>

5.  <span data-ttu-id="ec1fc-120">Fournissez une description pour la stratégie utilisateur d’accès externe.</span><span class="sxs-lookup"><span data-stu-id="ec1fc-120">Provide a description for external access user policy.</span></span>

6.  <span data-ttu-id="ec1fc-121">Sélectionnez **Activer les communications avec les utilisateurs fédérés**.</span><span class="sxs-lookup"><span data-stu-id="ec1fc-121">Select **Enable communications with federated users**.</span></span>

7.  <span data-ttu-id="ec1fc-122">Sélectionnez **Activer les communications avec les utilisateurs fédérés XMPP**.</span><span class="sxs-lookup"><span data-stu-id="ec1fc-122">Select **Enable communications with XMPP federated users**.</span></span>

8.  <span data-ttu-id="ec1fc-123">Cliquez sur **Valider** pour enregistrer les modifications apportées à la stratégie de site ou utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ec1fc-123">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

