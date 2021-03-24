---
title: Informations ITAdmin sur le client RealWear pour Microsoft Teams (préversion)
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Une démonstration ITAdmin de Microsoft Teams pour le client RealWear.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: 222cb12e38061c81a860092f90bf42d5412fdb63
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092282"
---
# <a name="microsoft-teams-for-realwear"></a><span data-ttu-id="4f51f-103">Microsoft Teams pour RealWear</span><span class="sxs-lookup"><span data-stu-id="4f51f-103">Microsoft Teams for RealWear</span></span>

<span data-ttu-id="4f51f-104">Cet article traite du client Microsoft Teams pour les casques ou lunettes wearable RealWear.</span><span class="sxs-lookup"><span data-stu-id="4f51f-104">This article covers the Microsoft Teams client for RealWear head-mounted wearables.</span></span> <span data-ttu-id="4f51f-105">Les employés de bureau utilisant RealWear HMT-1 et HMT-1Z1 peuvent désormais collaborer avec un expert à distance grâce à l’utilisation des appels vidéo sur Teams.</span><span class="sxs-lookup"><span data-stu-id="4f51f-105">Frontline Workers using RealWear HMT-1 and HMT-1Z1 can now collaborate with a remote expert using video calling on Teams.</span></span> <span data-ttu-id="4f51f-106">Par l’intermédiaire d’une interface utilisateur vocale, Teams pour RealWear permet aux employés de conserver leurs mains libres à 100 %, tout en gardant une idée précise de la situation dans des environnements bruyants et dangereux.</span><span class="sxs-lookup"><span data-stu-id="4f51f-106">Through a voice-controlled user interface, Teams for RealWear allows field workers to remain 100% hands-free while maintaining situational awareness in loud and hazardous environments.</span></span> <span data-ttu-id="4f51f-107">Avec l’affichage en temps réel de ce qu’ils voient, les employés de terrain peuvent réduire le temps nécessaire pour résoudre des problèmes et limiter les risques d’interruption de service.</span><span class="sxs-lookup"><span data-stu-id="4f51f-107">By showing what they see in real-time, field workers can accelerate the time to resolve issues and reduce the risk of an expensive downtime.</span></span>

## <a name="how-to-deploy-microsoft-teams-for-realwear"></a><span data-ttu-id="4f51f-108">Comment déployer Microsoft Teams pour RealWear</span><span class="sxs-lookup"><span data-stu-id="4f51f-108">How to deploy Microsoft Teams for RealWear</span></span>

- <span data-ttu-id="4f51f-109">Des appareils RealWear mis à jour vers la version 11.2 ou ultérieure.</span><span class="sxs-lookup"><span data-stu-id="4f51f-109">RealWear devices updated to release 11.2 or above.</span></span> <span data-ttu-id="4f51f-110">Plus d’informations [ici](https://realwear.com/knowledge-center/configure-on-release-10/wireless-update/).</span><span class="sxs-lookup"><span data-stu-id="4f51f-110">More information [here](https://realwear.com/knowledge-center/configure-on-release-10/wireless-update/).</span></span>
- <span data-ttu-id="4f51f-111">Accès à [Prospective RealWear](https://cloud.realwear.com/) pour la distribution du client Microsoft Teams pour Realwear.</span><span class="sxs-lookup"><span data-stu-id="4f51f-111">Access to [RealWear Foresight](https://cloud.realwear.com/) for distributing the Microsoft Teams client for Realwear.</span></span>

## <a name="required-licenses"></a><span data-ttu-id="4f51f-112">Licences requises</span><span class="sxs-lookup"><span data-stu-id="4f51f-112">Required Licenses</span></span>

<span data-ttu-id="4f51f-113">Les licences Microsoft Teams font partie des abonnements Microsoft 365 et Office 365.</span><span class="sxs-lookup"><span data-stu-id="4f51f-113">Microsoft Teams licenses are part of Microsoft 365 and Office 365 subscriptions.</span></span> <span data-ttu-id="4f51f-114">Aucune licence supplémentaire n’est nécessaire pour l’utilisation de Teams pour RealWear.</span><span class="sxs-lookup"><span data-stu-id="4f51f-114">No additional licensing is required to use Teams for RealWear.</span></span> <span data-ttu-id="4f51f-115">Pour plus d’informations sur l'obtention de Teams, consultez  [Comment obtenir l’accès à Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b).</span><span class="sxs-lookup"><span data-stu-id="4f51f-115">For more information about getting Teams, check out [How do I get access to Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b).</span></span>

## <a name="managing-realwear-devices"></a><span data-ttu-id="4f51f-116">Gestion des appareils RealWear</span><span class="sxs-lookup"><span data-stu-id="4f51f-116">Managing RealWear devices</span></span>

### <a name="microsoft-endpoint-manager"></a><span data-ttu-id="4f51f-117">Gestionnaire de point de terminaison Microsoft</span><span class="sxs-lookup"><span data-stu-id="4f51f-117">Microsoft Endpoint Manager</span></span>

<span data-ttu-id="4f51f-118">Les appareils RealWear peuvent être gérés à l’aide du mode Administrateur d’appareil Android.</span><span class="sxs-lookup"><span data-stu-id="4f51f-118">RealWear devices can be managed using Android Device Administrator mode.</span></span> <span data-ttu-id="4f51f-119">La prise en charge de la gestion via Android Enterprise est limitée, car les appareils ne disposent pas de Google Mobile Services (GMS) pour le moment.</span><span class="sxs-lookup"><span data-stu-id="4f51f-119">Support for management via Android Enterprise is limited, as the devices currently don't have Google Mobile Services (GMS) available.</span></span>

- <span data-ttu-id="4f51f-120">Pour en savoir plus sur la gestion des appareils RealWear sur le Gestionnaire de point de terminaison Microsoft, voir [l’inscription de l’administrateur d’appareil Android dans Intune](/mem/intune/enrollment/android-enroll-device-administrator).</span><span class="sxs-lookup"><span data-stu-id="4f51f-120">To learn more about managing RealWear devices on Microsoft Endpoint Manager, see [Android device administrator enrollment in Intune](/mem/intune/enrollment/android-enroll-device-administrator).</span></span>
- <span data-ttu-id="4f51f-121">Pour plus d’informations sur les stratégies, voir [Comment utiliser Intune dans les environnements sans Google Mobile Services](/mem/intune/apps/manage-without-gms).</span><span class="sxs-lookup"><span data-stu-id="4f51f-121">For more details on policies, see [How to use Intune in environments without Google Mobile Services](/mem/intune/apps/manage-without-gms).</span></span>

### <a name="third-party-enterprise-mobility-managers-emms"></a><span data-ttu-id="4f51f-122">Fournisseurs d’EMM tiers (EMMs)</span><span class="sxs-lookup"><span data-stu-id="4f51f-122">Third-party Enterprise Mobility Managers (EMMs)</span></span>

<span data-ttu-id="4f51f-123">Pour obtenir des instructions sur les EMM tiers, voir [Fournisseurs d’EMM pris en charge](https://www.realwear.com/knowledge-center/configure-on-release-10/remote-from-a-web-browser/emm/).</span><span class="sxs-lookup"><span data-stu-id="4f51f-123">For guidance on third-party EMMs, see [Supported Enterprise Mobility Management Providers](https://www.realwear.com/knowledge-center/configure-on-release-10/remote-from-a-web-browser/emm/).</span></span>

## <a name="end-user-content"></a><span data-ttu-id="4f51f-124">Contenu de l’utilisateur final</span><span class="sxs-lookup"><span data-stu-id="4f51f-124">End-user content</span></span>

<span data-ttu-id="4f51f-125">Pour en savoir plus sur ce point de vue de l’utilisateur final, veuillez consulter [Utilisation de Microsoft Teams pour RealWear](https://support.office.com/article/using-microsoft-teams-for-realwear-af20d232-d18c-476f-8031-843a4edccd5f).</span><span class="sxs-lookup"><span data-stu-id="4f51f-125">For further reading on this from an end-user perspective, please check out [Using Microsoft Teams for RealWear](https://support.office.com/article/using-microsoft-teams-for-realwear-af20d232-d18c-476f-8031-843a4edccd5f).</span></span>