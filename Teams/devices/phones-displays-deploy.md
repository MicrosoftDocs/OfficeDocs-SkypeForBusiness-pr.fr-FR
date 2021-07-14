---
title: Déployer Teams téléphones mobiles et Teams’affichage à l’aide d’Intune
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: weizxue
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
search.appverid: MET150
localization_priority: Normal
description: Cet article fournit une vue d’ensemble des fonctionnalités qui sont Microsoft Teams aux affichages.
ms.openlocfilehash: ee5b536aaadaf458b6edf9b32dea299a3ecad9a0
ms.sourcegitcommit: f39484688800a3d22f361e660d0eeba974a44fb1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420819"
---
# <a name="deploy-teams-phones-and-teams-displays-using-intune"></a><span data-ttu-id="90bb3-103">Déployer Teams téléphones mobiles et Teams’affichage à l’aide d’Intune</span><span class="sxs-lookup"><span data-stu-id="90bb3-103">Deploy Teams phones and Teams displays using Intune</span></span>

<span data-ttu-id="90bb3-104">Cet article vous donne une vue d’ensemble de la façon de déployer.</span><span class="sxs-lookup"><span data-stu-id="90bb3-104">This article gives you an overview of how to deploy.</span></span> <span data-ttu-id="90bb3-105">Teams les téléphones et les Teams’affichage à l’aide d’Intune.</span><span class="sxs-lookup"><span data-stu-id="90bb3-105">Teams phones and Teams display using Intune.</span></span>

## <a name="conditional-access"></a><span data-ttu-id="90bb3-106">Accès conditionnel</span><span class="sxs-lookup"><span data-stu-id="90bb3-106">Conditional Access</span></span>

<span data-ttu-id="90bb3-107">L’accès conditionnel est Azure Active Directory (Azure AD) qui vous permet de vous assurer que les appareils qui accèdent à vos ressources Office 365 sont correctement gérés et sécurisés.</span><span class="sxs-lookup"><span data-stu-id="90bb3-107">Conditional Access is an Azure Active Directory (Azure AD) feature that helps you to ensure devices accessing your Office 365 resources are properly managed and are secure.</span></span>  <span data-ttu-id="90bb3-108">Si vous appliquez des stratégies d’accès conditionnel au service Teams, les appareils Android (y compris les téléphones Teams et les affichages Teams) qui accèdent à Teams doivent être inscrits à Intune et leurs paramètres doivent se conformer à vos stratégies.</span><span class="sxs-lookup"><span data-stu-id="90bb3-108">If you apply Conditional Access policies to the Teams service, Android devices (including Teams phones and Teams displays) that access Teams needs to be enrolled into Intune and their settings need to comply with your policies.</span></span>  <span data-ttu-id="90bb3-109">Si l’appareil n’est pas inscrit à Intune, ou s’il est inscrit mais que ses paramètres ne respectent pas vos stratégies, l’accès conditionnel empêche un utilisateur de se connecté ou d’utiliser l’application Teams sur l’appareil.</span><span class="sxs-lookup"><span data-stu-id="90bb3-109">If the device isn't enrolled into Intune, or if it's enrolled but its settings don't comply with your policies, Conditional Access will prevent a user from signing in to or using the Teams app on the device.</span></span>

<span data-ttu-id="90bb3-110">En règle générale, les stratégies de conformité définies dans Intune sont affectées à des groupes d’utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="90bb3-110">Typically, compliance policies defined within Intune are assigned to groups of users.</span></span>  <span data-ttu-id="90bb3-111">Cela signifie que si vous attribuez une politique de conformité Android à user@contoso.com, cette stratégie s’appliquera également à leur smartphone Android et à tout appareil Teams Android user@contoso.com connecté.</span><span class="sxs-lookup"><span data-stu-id="90bb3-111">This means that if you assign an Android compliance policy to user@contoso.com, that policy will apply equally to their Android smartphone and to any Android-based Teams device that user@contoso.com signs into.</span></span>

<span data-ttu-id="90bb3-112">Si vous utilisez l’accès conditionnel, qui nécessite l’application de l’inscription Intune, vous devez configurer deux éléments pour permettre le succès de votre inscription Intune :</span><span class="sxs-lookup"><span data-stu-id="90bb3-112">If you use Conditional Access, which requires Intune enrollment to be enforced, in your organization, there are a couple things you need to set up to allow for a successful Intune enrollment:</span></span>

- <span data-ttu-id="90bb3-113">**Licence Intune** L’utilisateur qui se Teams l’appareil doit être titulaire d’une licence pour Intune.</span><span class="sxs-lookup"><span data-stu-id="90bb3-113">**Intune license** The user signing into the Teams device must be licensed for Intune.</span></span>  <span data-ttu-id="90bb3-114">Tant que l’appareil Teams est connecté à un compte d’utilisateur dispose d’une licence Intune valide, l’appareil est automatiquement inscrit à Microsoft Intune dans le cadre du processus de inscription.</span><span class="sxs-lookup"><span data-stu-id="90bb3-114">As long as the Teams device is signed in to a user account that has a valid Intune license, the device will automatically be enrolled in Microsoft Intune as part of the sign-in process.</span></span>
- <span data-ttu-id="90bb3-115">**Configurer Intune** Un client Intune correctement configuré doit être configuré pour l’inscription administrateur d’appareils Android.</span><span class="sxs-lookup"><span data-stu-id="90bb3-115">**Configure Intune** You must have a properly configured Intune tenant set up for Android Device Administrator enrollment.</span></span>

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a><span data-ttu-id="90bb3-116">Configurer Intune pour qu’il s’Teams appareils Android</span><span class="sxs-lookup"><span data-stu-id="90bb3-116">Configure Intune to enroll Teams Android-based devices</span></span>

<span data-ttu-id="90bb3-117">Teams Les appareils Android sont gérés par Intune via la gestion de l’administrateur d’appareils Android (DA).</span><span class="sxs-lookup"><span data-stu-id="90bb3-117">Teams Android-based devices are managed by Intune via Android Device Administrator (DA) management.</span></span> <span data-ttu-id="90bb3-118">Pour que les appareils soient inscrits à Intune, il existe quelques étapes de base à suivre.</span><span class="sxs-lookup"><span data-stu-id="90bb3-118">Before devices can be enrolled into Intune, there are a few basic steps to perform.</span></span>  <span data-ttu-id="90bb3-119">Si vous gérez déjà des appareils avec Intune, vous avez probablement déjà effectué toutes ces choses.</span><span class="sxs-lookup"><span data-stu-id="90bb3-119">If you are already managing devices with Intune today, you probably have already done all these things.</span></span>  <span data-ttu-id="90bb3-120">Si ce n’est pas le cas, voici comment faire :</span><span class="sxs-lookup"><span data-stu-id="90bb3-120">If not, here’s what to do:</span></span>

> [!NOTE]
> - <span data-ttu-id="90bb3-121">Si les administrateurs des locataires souhaitent que les téléphones de zone commune soient inscrits à Intune, ils doivent ajouter une licence Intune au compte et suivre les étapes de l’inscription Intune.</span><span class="sxs-lookup"><span data-stu-id="90bb3-121">If tenant admins want common area phones to be enrolled into Intune, they need to add an Intune license to the account and follow the steps for Intune enrollment.</span></span>
> - <span data-ttu-id="90bb3-122">Si le compte d’utilisateur utilisé pour se connecter à un appareil Teams n’est pas titulaire d’une licence pour Intune, les stratégies de conformité et restrictions d’inscription Intune doivent être désactivées pour le compte.</span><span class="sxs-lookup"><span data-stu-id="90bb3-122">If the user account used to sign into a Teams device isn't licensed for Intune, Intune compliance policies and enrollment restrictions need to be disabled for the account.</span></span>



1. <span data-ttu-id="90bb3-123">Définissez Intune MDM (mobile device management) Authority.</span><span class="sxs-lookup"><span data-stu-id="90bb3-123">Set Intune MDM (mobile device management) Authority.</span></span>  

   <span data-ttu-id="90bb3-124">Si vous n’avez jamais utilisé Intune auparavant, vous devez définir l’autorité de gestion des périphériques mobiles avant de pouvoir inscrire des appareils.</span><span class="sxs-lookup"><span data-stu-id="90bb3-124">If you’ve never used Intune before, you need to set the MDM authority before you can enroll devices.</span></span> <span data-ttu-id="90bb3-125">Pour plus d’informations, voir [Définir l’autorité de gestion des appareils mobiles.](/intune/fundamentals/mdm-authority-set)</span><span class="sxs-lookup"><span data-stu-id="90bb3-125">For more information, see [Set the mobile device management authority](/intune/fundamentals/mdm-authority-set).</span></span>  <span data-ttu-id="90bb3-126">Cette étape n’est à réaliser qu’une seule fois lors de la création d’un client Intune.</span><span class="sxs-lookup"><span data-stu-id="90bb3-126">This is a one-time step that has to be done upon creating a new Intune tenant.</span></span>
1. <span data-ttu-id="90bb3-127">Activez l’inscription de l’administrateur d’appareils Android.</span><span class="sxs-lookup"><span data-stu-id="90bb3-127">Enable Android device administrator enrollment.</span></span>
  
   <span data-ttu-id="90bb3-128">Les appareils à base de Teams Android sont gérés en tant qu’appareils d’administrateur d’appareils avec Intune.</span><span class="sxs-lookup"><span data-stu-id="90bb3-128">Android-based Teams devices are managed as device administrator devices with Intune.</span></span>  <span data-ttu-id="90bb3-129">L’inscription de l’administrateur de périphérique est par défaut non créditée pour les nouveaux locataires.</span><span class="sxs-lookup"><span data-stu-id="90bb3-129">Device administrator enrollment is off by default for newly created tenants.</span></span> <span data-ttu-id="90bb3-130">Consultez [l’inscription de l’administrateur d’appareils Android.](/intune/enrollment/android-enroll-device-administrator)</span><span class="sxs-lookup"><span data-stu-id="90bb3-130">See [Android device administrator enrollment](/intune/enrollment/android-enroll-device-administrator).</span></span>
1. <span data-ttu-id="90bb3-131">Attribuer des licences aux utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="90bb3-131">Assign licenses to users.</span></span> 
 
   <span data-ttu-id="90bb3-132">Les utilisateurs Teams’appareils inscrits à Intune doivent se voir attribuer une licence Intune valide.</span><span class="sxs-lookup"><span data-stu-id="90bb3-132">Users of Teams devices enrolling to Intune must be assigned a valid Intune license.</span></span> <span data-ttu-id="90bb3-133">Pour plus d’informations, voir Attribuer des licences aux utilisateurs afin qu’ils peuvent [inscrire des appareils dans Intune.](/intune/fundamentals/licenses-assign)</span><span class="sxs-lookup"><span data-stu-id="90bb3-133">For more information, see [Assign licenses to users so they can enroll devices in Intune](/intune/fundamentals/licenses-assign).</span></span>
1. <span data-ttu-id="90bb3-134">Attribuer des stratégies de conformité d’administrateur d’appareils.</span><span class="sxs-lookup"><span data-stu-id="90bb3-134">Assign Device Administrator compliance policies.</span></span>  

   <span data-ttu-id="90bb3-135">a.</span><span class="sxs-lookup"><span data-stu-id="90bb3-135">a.</span></span> <span data-ttu-id="90bb3-136">Créer une stratégie de conformité d’administrateur d’appareil Android.</span><span class="sxs-lookup"><span data-stu-id="90bb3-136">Create an Android Device Administrator compliance policy.</span></span>

   <span data-ttu-id="90bb3-137">b.</span><span class="sxs-lookup"><span data-stu-id="90bb3-137">b.</span></span> <span data-ttu-id="90bb3-138">Affectez-la au groupe Azure Active Directory qui contient les utilisateurs qui doivent se Teams appareils mobiles.</span><span class="sxs-lookup"><span data-stu-id="90bb3-138">Assign it to the Azure Active Directory group that contains the users that will be signing into the Teams devices.</span></span> <span data-ttu-id="90bb3-139">Voir [Utiliser les stratégies de conformité pour définir des règles pour les appareils que vous gérez avec Intune.](/mem/intune/protect/device-compliance-get-started)</span><span class="sxs-lookup"><span data-stu-id="90bb3-139">See [Use compliance policies to set rules for devices you manage with Intune](/mem/intune/protect/device-compliance-get-started).</span></span>

## <a name="see-also"></a><span data-ttu-id="90bb3-140">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="90bb3-140">See also</span></span>

[<span data-ttu-id="90bb3-141">Téléphones pour Teams</span><span class="sxs-lookup"><span data-stu-id="90bb3-141">Phones for Teams</span></span>](phones-for-teams.md)

[<span data-ttu-id="90bb3-142">Téléphones IP certifiés pour les Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="90bb3-142">IP Phones certified for Microsoft Teams</span></span>](teams-ip-phones.md)

[<span data-ttu-id="90bb3-143">Teams affiche</span><span class="sxs-lookup"><span data-stu-id="90bb3-143">Teams displays</span></span>](teams-displays.md)

[<span data-ttu-id="90bb3-144">Gérer vos périphériques dans Teams</span><span class="sxs-lookup"><span data-stu-id="90bb3-144">Manage your devices in Teams</span></span>](device-management.md)

[<span data-ttu-id="90bb3-145">Teams Marketplace</span><span class="sxs-lookup"><span data-stu-id="90bb3-145">Teams Marketplace</span></span>](https://office.com/teamsdevices)