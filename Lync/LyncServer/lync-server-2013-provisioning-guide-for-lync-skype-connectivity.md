---
title: 'Lync Server 2013 : Guide de mise en service pour la connectivité Lync-Skype'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Provisioning guide for Lync-Skype connectivity
ms:assetid: 69adda9b-5b72-4538-9be6-079b2f462e09
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440173(v=OCS.15)
ms:contentKeyID: 57793363
ms.date: 11/26/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76eb0ed3fbfffc3a30794f1cc8652090235ecc88
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201731"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="provisioning-guide-for-lync-skype-connectivity-in-lync-server-2013"></a><span data-ttu-id="74ed2-102">Guide de mise en service pour la connectivité Lync-Skype dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74ed2-102">Provisioning guide for Lync-Skype connectivity in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74ed2-103">_**Dernière modification de la rubrique :** 2014-11-26_</span><span class="sxs-lookup"><span data-stu-id="74ed2-103">_**Topic Last Modified:** 2014-11-26_</span></span>

<span data-ttu-id="74ed2-104">Lync Server 2013 prend en charge la connectivité avec Skype.</span><span class="sxs-lookup"><span data-stu-id="74ed2-104">Lync Server 2013 supports connectivity with Skype.</span></span> <span data-ttu-id="74ed2-105">Cette connectivité permet à vos utilisateurs de Lync 2013 d’ajouter des contacts Skype à l’aide du compte Microsoft de l’utilisateur Skype (MSA).</span><span class="sxs-lookup"><span data-stu-id="74ed2-105">This connectivity enables your Lync 2013 users to add Skype contacts by using the Skype user’s Microsoft Account (MSA).</span></span> <span data-ttu-id="74ed2-106">Les clients Skype peuvent également ajouter des utilisateurs Lync à leur liste de contacts.</span><span class="sxs-lookup"><span data-stu-id="74ed2-106">Skype clients can also add Lync users to their contact list.</span></span> <span data-ttu-id="74ed2-107">En fonction des stratégies définies de manière administrative dans Lync Server, les utilisateurs Lync et Skype pourront communiquer à l’aide de la messagerie instantanée, voir la présence de chacun et lancer des appels audio et vidéo.</span><span class="sxs-lookup"><span data-stu-id="74ed2-107">Based on policies administratively set in Lync Server, Lync and Skype users will be able to communicate using instant messaging, see each other’s presence, and initiate audio and video calls.</span></span> <span data-ttu-id="74ed2-108">Lync-Skype Connectivity est également une fonctionnalité de Lync Online, qui peut être activée pour les clients Lync Online à partir du centre d’administration Lync dans le portail Office 365.</span><span class="sxs-lookup"><span data-stu-id="74ed2-108">Lync-Skype connectivity is also a feature of Lync Online, and can be enabled for Lync Online customers from the Lync Administration Center within the Office 365 portal.</span></span>

<div>

> [!IMPORTANT]  
> <span data-ttu-id="74ed2-109">Si Lync Server est déjà configuré pour se connecter à Windows Messenger à l’aide de la connectivité PIC (public Instant Messaging Connectivity), votre déploiement est déjà configuré pour la connectivité Lync-Skype.</span><span class="sxs-lookup"><span data-stu-id="74ed2-109">If Lync Server is already configured to connect with Windows Messenger by using Public Instant Messaging Connectivity (PIC), your deployment is already configured for Lync-Skype connectivity.</span></span> <span data-ttu-id="74ed2-110">La seule modification que vous souhaiterez peut-être envisager est de renommer votre entrée Messenger PIC existante comme Skype.</span><span class="sxs-lookup"><span data-stu-id="74ed2-110">The only change you may want to consider is to rename your existing Messenger PIC entry as Skype.</span></span> <span data-ttu-id="74ed2-111">Pour plus d’informations, reportez-vous à la rubrique Configurer le paramètre de fournisseur PIC Skype pour Lync plus loin dans ce guide.</span><span class="sxs-lookup"><span data-stu-id="74ed2-111">For details, see Configure the Skype PIC provider setting for Lync later in this guide.</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="74ed2-112">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="74ed2-112">In This Section</span></span>

  - [<span data-ttu-id="74ed2-113">Remarque relative à la connectivité Lync-Skype dans Lync Server 2013 pour les clients Lync Online</span><span class="sxs-lookup"><span data-stu-id="74ed2-113">Note about Lync-Skype connectivity in Lync Server 2013 for Lync Online customers</span></span>](lync-server-2013-note-about-lync-skype-connectivity-for-lync-on.md)

  - [<span data-ttu-id="74ed2-114">Accès au site de mise en service de la connectivité PIC (Public IM Connectivity) de Lync Server à partir de Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74ed2-114">Accessing the Lync Server public IM connectivity provisioning site from Lync Server 2013</span></span>](lync-server-2013-accessing-the-lync-server-public-im-connectivity-provisioning-site.md)

  - [<span data-ttu-id="74ed2-115">Activation de la connectivité Lync-Skype dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="74ed2-115">Enabling Lync-Skype connectivity in Lync Server 2013</span></span>](lync-server-2013-enabling-lync-skype-connectivity.md)

  - [<span data-ttu-id="74ed2-116">Utilisation de la connectivité Lync-Skype dans Lync Server 2013 en tant qu’utilisateur final</span><span class="sxs-lookup"><span data-stu-id="74ed2-116">Using Lync-Skype connectivity in Lync Server 2013 as an end user</span></span>](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

  - [<span data-ttu-id="74ed2-117">Forum aux questions : approvisionnement de Lync Server 2013 pour la connectivité Skype</span><span class="sxs-lookup"><span data-stu-id="74ed2-117">Frequently Asked Questions: Provisioning Lync Server 2013 for Skype connectivity</span></span>](lync-server-2013-frequently-asked-questions-provisioning-lync-server-for-skype-connectivity.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

