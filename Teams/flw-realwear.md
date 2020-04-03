---
title: Informations ITAdmin sur le client RealWear pour Microsoft Teams (préversion)
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: ''
description: Démonstration ITAdmin du client RealWear pour Microsoft Teams.
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
ms.openlocfilehash: 95d3ead9c85fc58fdc55cd321e55b0ff9ca76853
ms.sourcegitcommit: 708270f1fecab6b7b44345d57a8e12bc36d19c8b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "43102388"
---
# <a name="realwear-for-microsoft-teams"></a><span data-ttu-id="e15e4-103">RealWear pour Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e15e4-103">RealWear for Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="e15e4-104">Ceci est une préversion ou une fonctionnalité d'une publication anticipée.</span><span class="sxs-lookup"><span data-stu-id="e15e4-104">This is a preview or early release feature.</span></span>

<span data-ttu-id="e15e4-105">Cet article traite du client Microsoft Teams pour les casques ou lunettes wearable RealWear.</span><span class="sxs-lookup"><span data-stu-id="e15e4-105">This article covers the Microsoft Teams client for RealWear head-mounted wearables.</span></span> <span data-ttu-id="e15e4-106">Les employés de terrain utilisant RealWear HMT-1 et HMT-1Z1 peuvent désormais collaborer avec un expert à distance grâce à l’utilisation des appels vidéo sur Teams.</span><span class="sxs-lookup"><span data-stu-id="e15e4-106">FirstLine Workers using RealWear HMT-1 and HMT-1Z1 can now collaborate with a remote expert using video calling on Teams.</span></span> <span data-ttu-id="e15e4-107">Par l’intermédiaire d’une interface utilisateur vocale, Teams pour RealWear permet aux employés de conserver leurs mains libres à 100 %, tout en gardant une idée précise de la situation dans des environnements bruyants et dangereux.</span><span class="sxs-lookup"><span data-stu-id="e15e4-107">Through a voice-controlled user interface, Teams for RealWear allows field workers to remain 100% hands-free while maintaining situational awareness in loud and hazardous environments.</span></span> <span data-ttu-id="e15e4-108">Avec l’affichage en temps réel de ce qu’ils voient, les employés de terrain peuvent réduire le temps nécessaire pour résoudre des problèmes et limiter les risques d’interruption de service.</span><span class="sxs-lookup"><span data-stu-id="e15e4-108">By showing what they see in real-time, field workers can accelerate the time to resolve issues and reduce the risk of an expensive downtime.</span></span>

## <a name="how-to-deploy-microsoft-teams-for-realwear"></a><span data-ttu-id="e15e4-109">Comment déployer Microsoft Teams pour RealWear</span><span class="sxs-lookup"><span data-stu-id="e15e4-109">How to deploy Microsoft Teams for RealWear</span></span>

<span data-ttu-id="e15e4-110">Le client Microsoft Teams pour RealWear est actuellement en Préversion publique.</span><span class="sxs-lookup"><span data-stu-id="e15e4-110">Microsoft Teams client for RealWear is currently in Public Preview.</span></span> <span data-ttu-id="e15e4-111">Pour participer à cette version d’évaluation, vous aurez besoin des éléments suivants :</span><span class="sxs-lookup"><span data-stu-id="e15e4-111">To participate in this preview, you will need the following:</span></span>

<span data-ttu-id="e15e4-112">Des appareils RealWear mis à jour vers la version 10.5.0 ou ultérieure.</span><span class="sxs-lookup"><span data-stu-id="e15e4-112">RealWear devices updated to release 10.5.0 or above.</span></span> <span data-ttu-id="e15e4-113">Pour plus d’informations, [consultez cette page](https://realwear.com/knowledge-center/configure-on-release-10/wireless-update/).</span><span class="sxs-lookup"><span data-stu-id="e15e4-113">More information [here](https://realwear.com/knowledge-center/configure-on-release-10/wireless-update/).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e15e4-114">Inscrivez-vous [ici](https://www.realwear.com/solutions/microsoft-teams/#C1) pour accéder à Teams pour le client RealWear dans [RealWear Foresight](https://cloud.realwear.com/).</span><span class="sxs-lookup"><span data-stu-id="e15e4-114">Register [here](https://www.realwear.com/solutions/microsoft-teams/#C1) for access to Teams for RealWear client in [RealWear Foresight](https://cloud.realwear.com/).</span></span>

## <a name="required-licenses"></a><span data-ttu-id="e15e4-115">Licences requises</span><span class="sxs-lookup"><span data-stu-id="e15e4-115">Required Licenses</span></span>

<span data-ttu-id="e15e4-116">Les licences Microsoft Teams font partie des abonnements Office 365.</span><span class="sxs-lookup"><span data-stu-id="e15e4-116">Microsoft Teams licenses are part of Office 365 subscriptions.</span></span> <span data-ttu-id="e15e4-117">Aucune licence supplémentaire n’est nécessaire pour l’utilisation de Teams pour RealWear.</span><span class="sxs-lookup"><span data-stu-id="e15e4-117">No additional licensing is required to use Teams for RealWear.</span></span> <span data-ttu-id="e15e4-118">Pour plus d’informations sur l'obtention de Teams, consultez  [Comment obtenir l’accès à Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b).</span><span class="sxs-lookup"><span data-stu-id="e15e4-118">For more information about getting Teams, check out [How do I get access to Microsoft Teams](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b).</span></span>

## <a name="managing-realwear-devices"></a><span data-ttu-id="e15e4-119">Gestion des appareils RealWear</span><span class="sxs-lookup"><span data-stu-id="e15e4-119">Managing RealWear devices</span></span>

### <a name="microsoft-endpoint-manager"></a><span data-ttu-id="e15e4-120">Gestionnaire de point de terminaison Microsoft</span><span class="sxs-lookup"><span data-stu-id="e15e4-120">Microsoft Endpoint Manager</span></span>

<span data-ttu-id="e15e4-121">Les appareils RealWear peuvent être gérés à l’aide du mode Administrateur d’appareil Android.</span><span class="sxs-lookup"><span data-stu-id="e15e4-121">RealWear devices can be managed using Android Device Administrator mode.</span></span> <span data-ttu-id="e15e4-122">La prise en charge de la gestion via Android Enterprise est limitée, car les appareils ne disposent pas de Google Mobile Services (GMS) pour le moment.</span><span class="sxs-lookup"><span data-stu-id="e15e4-122">Support for management via Android Enterprise is limited, as the devices currently don't have Google Mobile Services (GMS) available.</span></span>

- <span data-ttu-id="e15e4-123">Pour en savoir plus sur la gestion des appareils RealWear sur le Gestionnaire de point de terminaison Microsoft, voir l’[l’inscription de l’administrateur d’appareil Android dans Intune](https://docs.microsoft.com/mem/intune/enrollment/android-enroll-device-administrator).</span><span class="sxs-lookup"><span data-stu-id="e15e4-123">To learn more about managing RealWear devices on Microsoft Endpoint Manager, see [Android device administrator enrollment in Intune](https://docs.microsoft.com/mem/intune/enrollment/android-enroll-device-administrator).</span></span>

### <a name="third-party-enterprise-mobility-managers-emms"></a><span data-ttu-id="e15e4-124">Fournisseurs d’EMM tiers (EMMs)</span><span class="sxs-lookup"><span data-stu-id="e15e4-124">Third-party Enterprise Mobility Managers (EMMs)</span></span>

<span data-ttu-id="e15e4-125">Pour obtenir des instructions sur les EMM tiers, voir [Fournisseurs d’EMM pris en charge](https://www.realwear.com/knowledge-center/configure-on-release-10/remote-from-a-web-browser/emm/).</span><span class="sxs-lookup"><span data-stu-id="e15e4-125">For guidance on third-party EMMs, see [Supported Enterprise Mobility Management Providers](https://www.realwear.com/knowledge-center/configure-on-release-10/remote-from-a-web-browser/emm/).</span></span>
