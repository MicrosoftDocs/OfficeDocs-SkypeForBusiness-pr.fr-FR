---
title: Vérifier la fédération et l’accès à distance pour les utilisateurs externes
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Après la transition de l’itinéraire de Fédération au serveur Edge 2019 de Skype entreprise Server, vous devez effectuer certains tests fonctionnels pour vérifier que la Fédération s’exécute comme prévu. Les tests pour l’accès utilisateur externe doivent inclure chaque type d’utilisateur externe pris en charge par votre organisation, y compris tout ou partie des éléments suivants.
ms.openlocfilehash: ea17cbc8643d864f464da8e8a582191504970059
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243767"
---
# <a name="verify-federation-and-remote-access-for-external-users"></a><span data-ttu-id="96a8e-104">Vérifier la fédération et l’accès à distance pour les utilisateurs externes</span><span class="sxs-lookup"><span data-stu-id="96a8e-104">Verify federation and remote access for external users</span></span>

<span data-ttu-id="96a8e-105">Après la transition de l’itinéraire de Fédération au serveur Edge 2019 de Skype entreprise Server, vous devez effectuer certains tests fonctionnels pour vérifier que la Fédération s’exécute comme prévu.</span><span class="sxs-lookup"><span data-stu-id="96a8e-105">After transitioning the federation route to the Skype for Business Server 2019 Edge Server, you should perform some functional tests to verify that federation performs as expected.</span></span> <span data-ttu-id="96a8e-106">Les tests pour l’accès utilisateur externe doivent inclure chaque type d’utilisateur externe pris en charge par votre organisation, y compris tout ou partie des éléments suivants.</span><span class="sxs-lookup"><span data-stu-id="96a8e-106">Tests for external user access should include each type of external user that your organization supports, including any or all of the following.</span></span>
  
### <a name="test-connectivity-of-external-users-and-external-access"></a><span data-ttu-id="96a8e-107">Tester la connectivité des utilisateurs externes et des accès externes</span><span class="sxs-lookup"><span data-stu-id="96a8e-107">Test connectivity of external users and external access</span></span>

- <span data-ttu-id="96a8e-108">Utilisateurs d’au moins un domaine fédéré, d’un utilisateur interne sur Skype entreprise Server 2019 et un utilisateur sur l’installation héritée.</span><span class="sxs-lookup"><span data-stu-id="96a8e-108">Users from at least one federated domain, an internal user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="96a8e-109">Testez la messagerie instantanée, la présence, les appels audio/vidéo (A/V) et le partage de bureau.</span><span class="sxs-lookup"><span data-stu-id="96a8e-109">Test instant messaging (IM), presence, audio/video (A/V), and desktop sharing.</span></span>
    
- <span data-ttu-id="96a8e-110">Utilisateurs de chaque fournisseur de services de messagerie instantanée publique pris en charge par votre organisation (et pour lequel la mise en service a été effectuée) communique avec un utilisateur sur Skype entreprise Server 2019 et un utilisateur sur l’installation héritée.</span><span class="sxs-lookup"><span data-stu-id="96a8e-110">Users of each public IM service provider that your organization supports (and for which provisioning has been completed) communicating with a user on Skype for Business Server 2019 and a user on the legacy install.</span></span> 
    
- <span data-ttu-id="96a8e-111">Vérifiez que les utilisateurs anonymes peuvent participer à des conférences.</span><span class="sxs-lookup"><span data-stu-id="96a8e-111">Verify that anonymous users are able to join conferences.</span></span>
    
- <span data-ttu-id="96a8e-112">Un utilisateur A hébergé une installation héritée à l’aide de l’accès distant aux utilisateurs (journalisation i nPour Lync Server/Skype entreprise hors de l’intranet, mais sans VPN) avec un utilisateur sur Skype entreprise Server 2019 et un utilisateur sur l’installation héritée.</span><span class="sxs-lookup"><span data-stu-id="96a8e-112">A user hosted on the legacy install using remote user access (logging i nto Lync Server/Skype for Business from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="96a8e-113">Testez la messagerie instantanée, la présence, A/V et le partage du bureau.</span><span class="sxs-lookup"><span data-stu-id="96a8e-113">Test IM, presence, A/V, and desktop sharing.</span></span>
    
- <span data-ttu-id="96a8e-114">Un utilisateur hébergé sur Skype entreprise Server 2019 à l’aide de l’accès des utilisateurs distants (connexion à Skype entreprise Server 2019 hors de l’intranet mais sans VPN) avec un utilisateur sur Skype entreprise Server 2019, et un utilisateur sur l’installation héritée.</span><span class="sxs-lookup"><span data-stu-id="96a8e-114">A user hosted on Skype for Business Server 2019 using remote user access (logging in to Skype for Business Server 2019 from outside the intranet but without VPN) with a user on Skype for Business Server 2019, and a user on the legacy install.</span></span> <span data-ttu-id="96a8e-115">Testez la messagerie instantanée, la présence, A/V et le partage du bureau.</span><span class="sxs-lookup"><span data-stu-id="96a8e-115">Test IM, presence, A/V, and desktop sharing.</span></span>
    

