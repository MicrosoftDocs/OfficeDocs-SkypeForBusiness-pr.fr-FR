---
title: 'Lync Server 2013 : configuration de la téléphonie pour un utilisateur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure telephony for a user
ms:assetid: 4546432e-c839-4517-a2c5-bc0d4d8c6a03
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520988(v=OCS.15)
ms:contentKeyID: 48183987
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3fe22d70f442eed0cda1bbf56e79fb0e0e21f8a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179731"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-telephony-for-a-user-in-lync-server-2013"></a><span data-ttu-id="1bb57-102">Configurer la téléphonie pour un utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1bb57-102">Configure telephony for a user in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1bb57-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="1bb57-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="1bb57-104">Les paramètres de téléphonie sont certains des paramètres individuels d’un compte d’utilisateur qui peuvent être configurés dans le panneau de configuration Lync Server pour l’utilisateur (autrement dit, si l’utilisateur a été activé pour Lync Server 2013 et que l’Organisation prend en charge la téléphonie).</span><span class="sxs-lookup"><span data-stu-id="1bb57-104">Telephony settings are some of the individual settings of a user account that can be configured in Lync Server Control Panel for the user (that is, if the individual user has been enabled for Lync Server 2013 and the organization supports telephony).</span></span>

<span data-ttu-id="1bb57-105">Les options de téléphonie d’utilisateur Lync Server incluent les éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="1bb57-105">Lync Server user telephony options include the following:</span></span>

  - <span data-ttu-id="1bb57-106">**Audio/vidéo désactivé**   l’utilisateur ne peut pas passer des appels audio et vidéo.</span><span class="sxs-lookup"><span data-stu-id="1bb57-106">**Audio/video disabled**   The user cannot make calls with audio and video.</span></span>

  - <span data-ttu-id="1bb57-107">**PC à PC seul**   l’utilisateur peut uniquement effectuer des appels audio ou vidéo de PC à PC.</span><span class="sxs-lookup"><span data-stu-id="1bb57-107">**PC-to-PC only**   The user can make only PC-to-PC audio or video calls.</span></span>

  - <span data-ttu-id="1bb57-108">**Voix entreprise l'**   utilisateur peut utiliser l’infrastructure Lync Server 2013 pour acheminer tous les appels entrants et sortants.</span><span class="sxs-lookup"><span data-stu-id="1bb57-108">**Enterprise Voice**   The user can use the Lync Server 2013 infrastructure to route all incoming and outgoing calls.</span></span> <span data-ttu-id="1bb57-109">L’utilisateur peut aussi effectuer des appels de PC à PC.</span><span class="sxs-lookup"><span data-stu-id="1bb57-109">The user can also make PC-to-PC calls.</span></span>

  - <span data-ttu-id="1bb57-110">**Contrôle d’appel distant**   l’utilisateur peut utiliser Lync Server 2013 pour contrôler le téléphone de bureau et peut également effectuer des appels de PC à PC.</span><span class="sxs-lookup"><span data-stu-id="1bb57-110">**Remote call control**   The user can use Lync Server 2013 to control the desktop phone, and can also make PC-to-PC calls.</span></span>

<span data-ttu-id="1bb57-111">Pour plus d’informations sur la configuration de la téléphonie pour une organisation, voir [configure Telephony for a User in Lync server 2013](lync-server-2013-configure-telephony-for-a-user.md) et [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="1bb57-111">For details about configuring telephony for an organization, see [Configure telephony for a user in Lync Server 2013](lync-server-2013-configure-telephony-for-a-user.md) and [Deploying Enterprise Voice in Lync Server 2013](lync-server-2013-deploying-enterprise-voice.md) in the Deployment documentation.</span></span>

<div>

## <a name="to-configure-telephony-for-a-specific-user-account"></a><span data-ttu-id="1bb57-112">Pour configurer la téléphonie pour un compte d’utilisateur spécifique</span><span class="sxs-lookup"><span data-stu-id="1bb57-112">To configure telephony for a specific user account</span></span>

1.  <span data-ttu-id="1bb57-113">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="1bb57-113">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1bb57-114">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1bb57-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1bb57-115">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1bb57-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1bb57-116">Dans la barre de navigation de gauche, cliquez sur **Utilisateurs**.</span><span class="sxs-lookup"><span data-stu-id="1bb57-116">In the left navigation bar, click **Users**.</span></span>

4.  <span data-ttu-id="1bb57-117">Dans la zone **Rechercher des utilisateurs**, tapez le début ou l’intégralité du nom d’affichage, du prénom, du nom de famille, du nom de compte SAM, de l’adresse SIP ou de l’URI de ligne du compte d’utilisateur souhaité, puis cliquez sur **Rechercher**.</span><span class="sxs-lookup"><span data-stu-id="1bb57-117">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>

5.  <span data-ttu-id="1bb57-118">Dans le tableau, cliquez sur le compte d’utilisateur que vous souhaitez modifier.</span><span class="sxs-lookup"><span data-stu-id="1bb57-118">In the table, click the user account that you want to modify.</span></span>

6.  <span data-ttu-id="1bb57-119">Dans le menu **Edition**, cliquez sur **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="1bb57-119">On the **Edit** menu, click **Modify**.</span></span>

7.  <span data-ttu-id="1bb57-120">Dans **Téléphonie**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="1bb57-120">In **Telephony**, do the following:</span></span>
    
      - <span data-ttu-id="1bb57-121">Pour désactiver les appels audio et vidéo pour l’utilisateur, cliquez sur **Audio/vidéo désactivé**.</span><span class="sxs-lookup"><span data-stu-id="1bb57-121">To disable audio and video calls for the user, click **Audio/video disabled**.</span></span>
    
      - <span data-ttu-id="1bb57-p103">Pour activer les communications audio de PC à PC pour l’utilisateur, mais pas le contrôle d’appel distant ou Voix Entreprise, cliquez sur **De PC à PC uniquement**. Spécifiez une valeur d’**URI de ligne** pour le téléphone dont se sert l’utilisateur pour les communications audio de PC à PC.</span><span class="sxs-lookup"><span data-stu-id="1bb57-p103">To enable PC-to-PC audio communications for the user, but not remote call control or Enterprise Voice, click **PC-to-PC only**. Specify a value for **Line URI** for the telephone that the user uses for PC-to-PC audio communications.</span></span>
    
      - <span data-ttu-id="1bb57-124">Pour acheminer les appels téléphoniques de l’utilisateur à l’aide de l’infrastructure Lync Server 2010 conformément à la classe de la stratégie de service, y compris la communication audio de PC à PC, cliquez sur **voix entreprise**.</span><span class="sxs-lookup"><span data-stu-id="1bb57-124">To route the user's phone calls by using the Lync Server 2010 infrastructure in accordance with the class of service policy, including PC-to-PC audio communication, click **Enterprise Voice**.</span></span> <span data-ttu-id="1bb57-125">Dans **URI de ligne**, spécifiez le numéro de téléphone pour Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="1bb57-125">In **Line URI**, specify the telephone number for Enterprise Voice.</span></span> <span data-ttu-id="1bb57-126">Dans **Stratégie de plan de numérotation** et **Stratégie de la voix**, spécifiez les stratégies appropriées pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="1bb57-126">In **Dial plan policy** and **Voice policy**, specify the appropriate policies for the user.</span></span> <span data-ttu-id="1bb57-127">Afin de spécifier des règles de normalisation pour la traduction des numéros de téléphone composés par l’utilisateur au format E.164, sélectionnez le profil d’emplacement approprié dans **Stratégie d’emplacement**.</span><span class="sxs-lookup"><span data-stu-id="1bb57-127">To specify the normalization rules for translating phone numbers dialed by the user to the E.164 format, select the appropriate location profile in **Location policy**.</span></span>
    
      - <span data-ttu-id="1bb57-128">Pour activer le contrôle d’appel distant, qui permet aux utilisateurs de contrôler leur ligne de téléphone de bureau à partir de Lync Server 2013 afin de passer des appels PC à PC et des appels PC à téléphone, cliquez sur **contrôle d’appel distant**.</span><span class="sxs-lookup"><span data-stu-id="1bb57-128">To enable remote call control, which enables users to control their desktop phone line from Lync Server 2013 to make PC-to-PC calls and PC-to-phone calls, click **Remote call control**.</span></span> <span data-ttu-id="1bb57-129">Dans **URI de ligne**, spécifiez le numéro de téléphone pour le contrôle d’appel distant.</span><span class="sxs-lookup"><span data-stu-id="1bb57-129">In **Line URI**, specify the telephone number for remote call control.</span></span> <span data-ttu-id="1bb57-130">L’utilisateur doit disposer d’un téléphone de bureau et d’une connexion d’autocommutateur privé (PBX) pour le routage des appels.</span><span class="sxs-lookup"><span data-stu-id="1bb57-130">The user must have a desktop phone and private branch exchange (PBX) connection for call routing.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1bb57-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1bb57-131">See Also</span></span>


[<span data-ttu-id="1bb57-132">Modification des propriétés d’un compte d’utilisateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1bb57-132">Modifying user account properties in Lync Server 2013</span></span>](lync-server-2013-modifying-user-account-properties.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

