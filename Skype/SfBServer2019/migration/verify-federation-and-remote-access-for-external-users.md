---
title: Vérifier la fédération et l’accès à distance pour les utilisateurs externes
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Après avoir effectué la transition de l’itinéraire de fédération vers le serveur Edge Skype Entreprise Server 2019, vous devez effectuer des tests fonctionnels pour vérifier que la fédération fonctionne comme prévu. Les tests relatifs à l’accès des utilisateurs externes doivent inclure chaque type d’utilisateur externe pris en charge par votre organisation, notamment une partie ou l’ensemble de ce qui suit.
ms.openlocfilehash: b2567f4e46bd39d2748e3a4a3ba6cc5d6c197b11
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751666"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="4950c-104">Vérifier la fédération et l’accès à distance pour les utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="4950c-104">Verify federation and remote access for external users</span></span>

<span data-ttu-id="4950c-105">Après avoir effectué la transition de l’itinéraire de fédération vers le serveur Edge Skype Entreprise Server 2019, vous devez effectuer des tests fonctionnels pour vérifier que la fédération fonctionne comme prévu.</span><span class="sxs-lookup"><span data-stu-id="4950c-105">After transitioning the federation route to the Skype for Business Server 2019 Edge Server, you should perform some functional tests to verify that federation performs as expected.</span></span> <span data-ttu-id="4950c-106">Les tests relatifs à l’accès des utilisateurs externes doivent inclure chaque type d’utilisateur externe pris en charge par votre organisation, notamment une partie ou l’ensemble de ce qui suit.</span><span class="sxs-lookup"><span data-stu-id="4950c-106">Tests for external user access should include each type of external user that your organization supports, including any or all of the following.</span></span>
  
### <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="4950c-107">Tester la connectivité des utilisateurs externes et de l’accès externe</span><span class="sxs-lookup"><span data-stu-id="4950c-107">Test connectivity of external users and external access</span></span>

- <span data-ttu-id="4950c-108">Utilisateurs d’au moins un domaine fédéré, d’un utilisateur interne sur Skype Entreprise Server 2019 et d’un utilisateur sur l’installation héritée.</span><span class="sxs-lookup"><span data-stu-id="4950c-108">Users from at least one federated domain, an internal user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="4950c-109">Testez la messagerie instantanée, la présence, l’audio/vidéo (A/V) et le partage de Bureau.</span><span class="sxs-lookup"><span data-stu-id="4950c-109">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>
    
- <span data-ttu-id="4950c-110">Utilisateurs de chaque fournisseur de services de messagerie instantanée public pris en charge par votre organisation (et pour lequel la mise en service a été terminée) communiquant avec un utilisateur sur Skype Entreprise Server 2019 et un utilisateur sur l’installation héritée.</span><span class="sxs-lookup"><span data-stu-id="4950c-110">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Skype for Business Server 2019 and a user on the legacy install.</span></span> 
    
- <span data-ttu-id="4950c-111">Vérifiez que les utilisateurs anonymes peuvent participer à des conférences.</span><span class="sxs-lookup"><span data-stu-id="4950c-111">Verify that anonymous users are able to join conferences.</span></span>
    
- <span data-ttu-id="4950c-112">Utilisateur hébergé sur l’installation héritée à l’aide de l’accès des utilisateurs distants (enregistrement i nto Lync Server/Skype Entreprise en dehors de l’intranet mais sans VPN) avec un utilisateur sur Skype Entreprise Server 2019 et un utilisateur sur l’installation héritée.</span><span class="sxs-lookup"><span data-stu-id="4950c-112">A user hosted on the legacy install using remote user access (logging i nto Lync Server/Skype for Business from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="4950c-113">Testez la messagerie instantanée, la présence, l’audio/vidéo et le partage de Bureau.</span><span class="sxs-lookup"><span data-stu-id="4950c-113">Test IM, presence, A/V, and desktop sharing.</span></span>
    
- <span data-ttu-id="4950c-114">Utilisateur hébergé sur Skype Entreprise Server 2019 à l’aide de l’accès des utilisateurs distants (connexion à Skype Entreprise Server 2019 en dehors de l’intranet mais sans VPN) avec un utilisateur sur Skype Entreprise Server 2019 et un utilisateur sur l’installation héritée.</span><span class="sxs-lookup"><span data-stu-id="4950c-114">A user hosted on Skype for Business Server 2019 using remote user access (logging in to Skype for Business Server 2019 from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="4950c-115">Testez la messagerie instantanée, la présence, l’audio/vidéo et le partage de Bureau.</span><span class="sxs-lookup"><span data-stu-id="4950c-115">Test IM, presence, A/V, and desktop sharing.</span></span>
    

