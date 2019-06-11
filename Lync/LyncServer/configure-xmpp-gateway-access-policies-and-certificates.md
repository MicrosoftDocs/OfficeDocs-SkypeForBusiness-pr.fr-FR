---
title: Configuration des certificats et des stratégies d’accès de passerelle XMPP
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configure XMPP gateway access policies and certificates
ms:assetid: fac02f4e-d14d-4be3-b53c-74c82436fd93
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721945(v=OCS.15)
ms:contentKeyID: 49733882
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f545fd7681e492440419aee600635858bf7bfdef
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838847"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-access-policies-and-certificates"></a><span data-ttu-id="90ba9-102">Configuration des certificats et des stratégies d’accès de passerelle XMPP</span><span class="sxs-lookup"><span data-stu-id="90ba9-102">Configure XMPP gateway access policies and certificates</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="90ba9-103">_**Dernière modification de la rubrique:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="90ba9-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="90ba9-104">La Fédération XMPP définit un déploiement externe en fonction du protocole XMPP (eXtensible Messaging and Presence Protocol).</span><span class="sxs-lookup"><span data-stu-id="90ba9-104">XMPP federation defines an external deployment based on the eXtensible Messaging and Presence Protocol (XMPP).</span></span> <span data-ttu-id="90ba9-105">Une configuration XMPP permet aux utilisateurs de Lync d’accéder aux utilisateurs de domaine XMPP en procédant comme suit:</span><span class="sxs-lookup"><span data-stu-id="90ba9-105">An XMPP configuration allows Lync users access to XMPP domain users by:</span></span>

  - <span data-ttu-id="90ba9-106">Messagerie instantanée et présence-personne à personne uniquement</span><span class="sxs-lookup"><span data-stu-id="90ba9-106">IM and Presence – person to person only</span></span>

  - <span data-ttu-id="90ba9-107">Créer des contacts fédérés de XMPP dans le client Lync</span><span class="sxs-lookup"><span data-stu-id="90ba9-107">Creation of XMPP federated contacts in the Lync client</span></span>

<span data-ttu-id="90ba9-108">Lorsque vous configurez des stratégies pour la prise en charge des partenaires fédérés du protocole de messagerie extensible et de présence, les stratégies s’appliquent aux utilisateurs des domaines fédérés de XMPP, mais pas aux utilisateurs de services de messagerie instantanée SIP (Session Initiation Protocol). (par exemple, Windows Live) ou domaines fédérés SIP.</span><span class="sxs-lookup"><span data-stu-id="90ba9-108">When you configure policies for support of extensible messaging and presence protocol (XMPP) federated partners, the policies apply to users of XMPP federated domains, but not to users of session initiation protocol (SIP) instant messaging (IM) service providers (for example, Windows Live), or SIP federated domains.</span></span> <span data-ttu-id="90ba9-109">Vous configurez un partenaire fédéré de XMPP pour chaque domaine fédéré XMPP que vous voulez autoriser vos utilisateurs à ajouter des contacts et à communiquer avec eux.</span><span class="sxs-lookup"><span data-stu-id="90ba9-109">You configure an XMPP Federated Partner for each XMPP federated domain that you want to allow your users to add contacts and communicate with.</span></span> <span data-ttu-id="90ba9-110">Une fois les stratégies en place, vous devez configurer les certificats de passerelle XMPP.</span><span class="sxs-lookup"><span data-stu-id="90ba9-110">Once the policies are in place, you need to configure the XMPP Gateway certificates.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="90ba9-111">Pour lancer la migration de la passerelle XMPP, vous devez déployer la passerelle de Lync Server 2013 XMPP et configurer des stratégies d’accès pour permettre aux utilisateurs de Lync Server 2013 la passerelle XMPP.</span><span class="sxs-lookup"><span data-stu-id="90ba9-111">To begin the XMPP Gateway migration, you need to deploy the Lync Server 2013 XMPP Gateway, and configure access policies to enable users for Lync Server 2013 XMPP Gateway.</span></span> <span data-ttu-id="90ba9-112">Pour pouvoir effectuer cette procédure, tous les utilisateurs doivent être déplacés vers le déploiement Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="90ba9-112">All users must be moved to the Lync Server 2013 deployment before you perform these steps.</span></span> <span data-ttu-id="90ba9-113">Pour plus d’informations, consultez <A href="configure-xmpp-gateway-on-lync-server-2013.md">configurer la passerelle XMPP sur Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="90ba9-113">For details, see <A href="configure-xmpp-gateway-on-lync-server-2013.md">Configure XMPP gateway on Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="configure-an-external-access-policy-to-enable-users-for-lync-server-2013-xmpp-gateway"></a><span data-ttu-id="90ba9-114">Configurer une stratégie d’accès externe pour permettre aux utilisateurs de Lync Server 2013-passerelle XMPP</span><span class="sxs-lookup"><span data-stu-id="90ba9-114">Configure an External Access Policy to Enable Users for Lync Server 2013 XMPP Gateway</span></span>

1.  <span data-ttu-id="90ba9-115">Ouvrez le Paneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="90ba9-115">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="90ba9-116">Dans la barre de navigation de gauche, cliquez sur **Fédération et accès externe**, puis sur **stratégie d’accès externe**.</span><span class="sxs-lookup"><span data-stu-id="90ba9-116">In the left navigation bar, click **Federation and External Access**, and then click **External Access Policy**.</span></span>

3.  <span data-ttu-id="90ba9-117">Cliquez sur **nouveau** , puis sur stratégie de l' **utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="90ba9-117">Click **New** and then click **User policy**.</span></span>

4.  <span data-ttu-id="90ba9-118">Entrez le nom de la stratégie de l’utilisateur pour l’accès externe.</span><span class="sxs-lookup"><span data-stu-id="90ba9-118">Enter a name for the external access user policy.</span></span>

5.  <span data-ttu-id="90ba9-119">Entrez une description pour la stratégie utilisateur d’accès externe.</span><span class="sxs-lookup"><span data-stu-id="90ba9-119">Provide a description for external access user policy.</span></span>

6.  <span data-ttu-id="90ba9-120">Sélectionnez **activer les communications avec les utilisateurs fédérés**.</span><span class="sxs-lookup"><span data-stu-id="90ba9-120">Select **Enable communications with federated users**.</span></span>

7.  <span data-ttu-id="90ba9-121">Sélectionnez **activer les communications avec les utilisateurs fédérés de XMPP**.</span><span class="sxs-lookup"><span data-stu-id="90ba9-121">Select **Enable communications with XMPP federated users**.</span></span>

8.  <span data-ttu-id="90ba9-122">Cliquez sur **valider** pour enregistrer les modifications apportées à la stratégie de site ou d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="90ba9-122">Click **Commit** to save your changes to the site or user policy.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

