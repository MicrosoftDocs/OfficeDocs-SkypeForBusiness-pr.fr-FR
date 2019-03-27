---
title: Vérifier la fédération et l’accès à distance pour les utilisateurs externes
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Après la transition de l’itinéraire de fédération pour le Skype pour le serveur de périphérie 2019 Business Server, vous devez effectuer des tests fonctionnels pour vérifier que la fédération fonctionne comme prévu. Tests pour l’accès des utilisateurs externes doivent inclure chaque type d’utilisateur externe prenant en charge votre organisation, dont un ou plusieurs des options suivantes.
ms.openlocfilehash: 3a520b39d76ab93f4ec7fcaacd139b3f83a3326a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876696"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="24bb9-104">Vérifier la fédération et l’accès à distance pour les utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="24bb9-104">Verify federation and remote access for external users</span></span>

<span data-ttu-id="24bb9-105">Après la transition de l’itinéraire de fédération pour le Skype pour le serveur de périphérie 2019 Business Server, vous devez effectuer des tests fonctionnels pour vérifier que la fédération fonctionne comme prévu.</span><span class="sxs-lookup"><span data-stu-id="24bb9-105">After transitioning the federation route to the Skype for Business Server 2019 Edge Server, you should perform some functional tests to verify that federation performs as expected.</span></span> <span data-ttu-id="24bb9-106">Tests pour l’accès des utilisateurs externes doivent inclure chaque type d’utilisateur externe prenant en charge votre organisation, dont un ou plusieurs des options suivantes.</span><span class="sxs-lookup"><span data-stu-id="24bb9-106">Tests for external user access should include each type of external user that your organization supports, including any or all of the following.</span></span>
  
### <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="24bb9-107">Tester la connectivité des utilisateurs externes et l’accès externe</span><span class="sxs-lookup"><span data-stu-id="24bb9-107">Test connectivity of external users and external access</span></span>

- <span data-ttu-id="24bb9-108">Les utilisateurs d’au moins un domaine fédéré, un utilisateur interne sur Skype pour Business Server 2019 et un utilisateur hérité installent.</span><span class="sxs-lookup"><span data-stu-id="24bb9-108">Users from at least one federated domain, an internal user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="24bb9-109">Tester la messagerie instantanée, présence, audio/vidéo (A / V) et le partage du bureau.</span><span class="sxs-lookup"><span data-stu-id="24bb9-109">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>
    
- <span data-ttu-id="24bb9-110">Les utilisateurs de chaque fournisseur de services de messagerie instantanée publique qui prend en charge de votre organisation (et pour lequel le provisionnement a été effectué) communiquant avec un utilisateur sur Skype pour Business Server 2019 et un utilisateur sur l’installation héritée.</span><span class="sxs-lookup"><span data-stu-id="24bb9-110">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Skype for Business Server 2019 and a user on the legacy install.</span></span> 
    
- <span data-ttu-id="24bb9-111">Vérifier que les utilisateurs anonymes peuvent participer à des conférences.</span><span class="sxs-lookup"><span data-stu-id="24bb9-111">Verify that anonymous users are able to join conferences.</span></span>
    
- <span data-ttu-id="24bb9-112">Un utilisateur hébergé sur hérité installer à l’aide de l’accès des utilisateurs distants (journalisation i /nPour Lync Server/Skype pour les entreprises à partir de l’extérieur de l’intranet, mais sans VPN) à un utilisateur sur Skype pour Business Server 2019 et un utilisateur sur l’installation héritée.</span><span class="sxs-lookup"><span data-stu-id="24bb9-112">A user hosted on the legacy install using remote user access (logging i nto Lync Server/Skype for Business from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="24bb9-113">Test de messagerie instantanée, présence, A / V et du bureau de partage.</span><span class="sxs-lookup"><span data-stu-id="24bb9-113">Test IM, presence, A/V, and desktop sharing.</span></span>
    
- <span data-ttu-id="24bb9-114">Un utilisateur hébergé sur Skype pour Business Server 2019 à l’aide de l’accès des utilisateurs distants (connexion à Skype pour Business Server 2019 à partir de l’extérieur de l’intranet, mais sans VPN) avec un utilisateur sur Skype pour Business Server 2019 et un utilisateur sur l’installation héritée.</span><span class="sxs-lookup"><span data-stu-id="24bb9-114">A user hosted on Skype for Business Server 2019 using remote user access (logging in to Skype for Business Server 2019 from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="24bb9-115">Test de messagerie instantanée, présence, A / V et du bureau de partage.</span><span class="sxs-lookup"><span data-stu-id="24bb9-115">Test IM, presence, A/V, and desktop sharing.</span></span>
    

