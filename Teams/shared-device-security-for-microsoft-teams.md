---
title: Guide de sécurité pour Microsoft Teams
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.date: 08/21/2020
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: pawa
description: Conseils pour utiliser Microsoft Teams en toute sécurité à partir d'un ordinateur partagé sur le lieu de travail.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
ms.custom:
- Security
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3486df0ca12303a9351c756df4184f160e95ab34
ms.sourcegitcommit: 32023931b607542cffadef74383e3ecd47db4ab6
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/25/2020
ms.locfileid: "46868693"
---
# <a name="use-microsoft-teams-securely-on-shared-computers"></a><span data-ttu-id="0fb6d-103">Utiliser les Teams Microsoft en toute sécurité sur des ordinateurs partagés</span><span class="sxs-lookup"><span data-stu-id="0fb6d-103">Use Microsoft Teams securely on shared computers</span></span>

<span data-ttu-id="0fb6d-104">Dans la mesure du possible*il est recommandé* aux entreprises d'adopter une approche de confiance zéro pour les appareils clients en utilisant les capacités de gestion des appareils, les contrôles de santé des appareils et l'application des politiques, le cryptage au niveau des appareils et d'autres caractéristiques de sécurité.</span><span class="sxs-lookup"><span data-stu-id="0fb6d-104">When possible, it is *recommended* Enterprises make use of a Zero Trust approach to client devices making use of device management capabilities, device health checks and policy enforcement, device-level encryption, and other security features.</span></span>

:::image type="content" source="media/tp_ZeroTrustPrinciples.PNG" alt-text="Image de confiance zéro montrant la vérification explicite, le moindre privilège, et l'hypothèse de violation -- les principes fondamentaux de confiance zéro -- dans les cercles bleus.":::

<span data-ttu-id="0fb6d-106">Les administrateurs peuvent créer des conditions très sûres en *insistant* sur la vérification, le moindre privilège, et en assumant des compromis -- des normes qui conduisent à des actions qui minimisent les risques à la fois pour les utilisateurs et les données.</span><span class="sxs-lookup"><span data-stu-id="0fb6d-106">Administrators can create very secure conditions by *insisting* on verification, least privilege, and by assuming compromise -- standards that lead to actions that minimize risk to both users and data.</span></span>

> [!TIP]
> <span data-ttu-id="0fb6d-107">Pour un examen plus approfondi des principes de la confiance zéro, voir [ces vidéos](https://docs.microsoft.com/security/ciso-workshop/ciso-workshop-module-3#part-2-zero-trust-definition-and-models-1537).</span><span class="sxs-lookup"><span data-stu-id="0fb6d-107">For a deeper examination of Zero Trust principles, see [these videos](https://docs.microsoft.com/security/ciso-workshop/ciso-workshop-module-3#part-2-zero-trust-definition-and-models-1537).</span></span>

## <a name="tips-for-using-microsoft-teams-securely-from-a-shared-computer"></a><span data-ttu-id="0fb6d-108">Conseils pour utiliser Microsoft Teams en toute sécurité à partir d'un ordinateur partagé</span><span class="sxs-lookup"><span data-stu-id="0fb6d-108">Tips for using Microsoft Teams securely from a shared computer</span></span>

<span data-ttu-id="0fb6d-109">Reconnaissant que cela peut ne pas être possible ou pratique dans tous les scénarios, il est toujours important que les administrateurs de la sécurité suivent les conseils pour utiliser au mieux Teams à partir d'un ordinateur partagé ou d'un appareil non géré.</span><span class="sxs-lookup"><span data-stu-id="0fb6d-109">Recognizing that this may not be possible or practical in all scenarios, it is still important for security administrators to follow guidance for using Teams from a shared computer or unmanaged device as best they can.</span></span>

<span data-ttu-id="0fb6d-110">Des plans doivent être élaborés pour se conformer aux lignes directrices aussi rapidement que possible.</span><span class="sxs-lookup"><span data-stu-id="0fb6d-110">Plans should be developed to adhere to guidelines as promptly as is possible.</span></span>

1. <span data-ttu-id="0fb6d-111">Utiliser les capacités de sécurité de la plate-forme du système opérationnel.</span><span class="sxs-lookup"><span data-stu-id="0fb6d-111">Make use of Operating System platform security capabilities.</span></span>
    1. <span data-ttu-id="0fb6d-112">Assurez-vous que le système opérationnel est configuré pour installer les mises à jour automatiques du fournisseur du système opérationnel (pour les systèmes Microsoft, cela peut être fait via [**Windows Update**](https://support.microsoft.com/help/12373/windows-update-faq)).</span><span class="sxs-lookup"><span data-stu-id="0fb6d-112">Ensure that the operating system is configured to install automatic updates from the Operating System provider (for Microsoft systems, this can be accomplished via [**Windows Update**](https://support.microsoft.com/help/12373/windows-update-faq)).</span></span> 
    2. <span data-ttu-id="0fb6d-113">Assurez-vous que toutes les capacités de cryptage de l'appareil, telles que [**bitlocker**](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview) sont activées et que la clé utilisée pour accéder à l'appareil est sécurisée.</span><span class="sxs-lookup"><span data-stu-id="0fb6d-113">Ensure that any device encryption capabilities such as [**bitlocker**](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview) are enabled, and the key used to access the device is secured.</span></span>  <span data-ttu-id="0fb6d-114">Notez que la plupart des appareils modernes [**Windows 10 prennent en charge bitlocker**](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10).</span><span class="sxs-lookup"><span data-stu-id="0fb6d-114">Note that most modern [**Windows 10 devices support bitlocker**](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-device-encryption-overview-windows-10).</span></span> 
    1. <span data-ttu-id="0fb6d-115">Utilisez des capacités anti-virus telles que celles offertes par [**Windows Defender**](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) sur vos appareils.</span><span class="sxs-lookup"><span data-stu-id="0fb6d-115">Use anti-virus capabilities such as those offered by [**Windows Defender**](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) on your devices.</span></span>
    1. <span data-ttu-id="0fb6d-116">L'utilisation [de comptes d'utilisateur séparés ](https://support.microsoft.com/help/4026923/windows-10-create-a-local-user-or-administrator-account)pour chaque utilisateur du système est fortement recommandée.</span><span class="sxs-lookup"><span data-stu-id="0fb6d-116">Use of [separate user accounts](https://support.microsoft.com/help/4026923/windows-10-create-a-local-user-or-administrator-account) for each user of the system is highly recommended.</span></span>
    1. <span data-ttu-id="0fb6d-117">*Ne*pas accorder, ou utiliser, des privilèges d'administrateur pour des fonctions non administratives (telles que la navigation sur le web, la gestion des Teams etc).</span><span class="sxs-lookup"><span data-stu-id="0fb6d-117">*Do not* grant, or use, administrator privileges for non-administrative functions (such as browsing the web, running Teams, et cetera).</span></span>

2. <span data-ttu-id="0fb6d-118">Exploiter les capacités de sécurité du navigateur.</span><span class="sxs-lookup"><span data-stu-id="0fb6d-118">Leverage browser security capabilities.</span></span>
    1. <span data-ttu-id="0fb6d-119">Utilisez des sessions de navigation privées pour minimiser les données et l'historique qui persistent sur le disque.</span><span class="sxs-lookup"><span data-stu-id="0fb6d-119">Use private browsing sessions to minimize data and history that persists to disk.</span></span> <span data-ttu-id="0fb6d-120">Par exemple, utilisez [la navigation inPrivate dans Microsoft Edge ](https://support.microsoft.com/help/4533513/microsoft-edge-browse-inprivate), [ la navigation Incognito dans Google Chrome](https://support.google.com/chrome/answer/95464?co=GENIE.Platform%3DDesktop&hl=en), ou les capacités de votre navigateur spécifique pour la navigation privée.</span><span class="sxs-lookup"><span data-stu-id="0fb6d-120">For example, use [inPrivate browsing in Microsoft Edge](https://support.microsoft.com/help/4533513/microsoft-edge-browse-inprivate), [Incognito browsing in Google Chrome](https://support.google.com/chrome/answer/95464?co=GENIE.Platform%3DDesktop&hl=en), or the capabilities your specific browser for browsing privately.</span></span> 
    1. <span data-ttu-id="0fb6d-121">Il est recommandé de changer le comportement du système afin d'engager la navigation privée*par défaut*.</span><span class="sxs-lookup"><span data-stu-id="0fb6d-121">Changing the system behavior to engage private browsing *by default* is recommended.</span></span> 

3. <span data-ttu-id="0fb6d-122">Naviguez et utilisez [l'application web Teams](https://teams.microsoft.com) (parfois appelée le  *client* web) et non le client téléchargeable Teams.</span><span class="sxs-lookup"><span data-stu-id="0fb6d-122">Browse to and use the [Teams web app](https://teams.microsoft.com) (sometimes called the *web* client) not the downloadable Teams client.</span></span>

4. <span data-ttu-id="0fb6d-123">Lorsque vous avez fini d'utiliser le système partagé, vous devez :</span><span class="sxs-lookup"><span data-stu-id="0fb6d-123">When you are done using the shared system, you must:</span></span> 
    1. <span data-ttu-id="0fb6d-124">[ Déconnexion des Teams](https://support.microsoft.com/office/sign-out-of-teams-a6d76e69-e1dd-4bc4-8e5f-04ba48384487).</span><span class="sxs-lookup"><span data-stu-id="0fb6d-124">[Sign out of Teams](https://support.microsoft.com/office/sign-out-of-teams-a6d76e69-e1dd-4bc4-8e5f-04ba48384487).</span></span>
    1. <span data-ttu-id="0fb6d-125">Fermez tous les onglets et fenêtres du navigateur.</span><span class="sxs-lookup"><span data-stu-id="0fb6d-125">Close all browser tabs and windows.</span></span>
    1. <span data-ttu-id="0fb6d-126">Déconnectez-vous de l'appareil.</span><span class="sxs-lookup"><span data-stu-id="0fb6d-126">Sign out of the device.</span></span>

<span data-ttu-id="0fb6d-127">Les éléments ci-dessus ne constituent pas une liste exhaustive des meilleures pratiques ou des contrôles de sécurité couvrant tous les cas, et il se peut que des mesures supplémentaires puissent être prises dans votre environnement (par exemple, les administrateurs de la sécurité peuvent choisir d'utiliser des liens et des pièces jointes sûrs pour les Teams si vous avez [Office 365 ATP Plan 1 ou 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide#office-365-atp-plan-1-and-plan-2)).</span><span class="sxs-lookup"><span data-stu-id="0fb6d-127">The items above are not a comprehensive list of best practices or security controls covering all cases, and there may be extra actions that can be taken in your environment, (for instance, security administrators may choose to use Safe Links and Safe Attachments for Teams if you have [Office 365 ATP Plan 1 or 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide#office-365-atp-plan-1-and-plan-2)).</span></span> <span data-ttu-id="0fb6d-128">Toutefois, ces étapes constituent un point de départ pour l'élaboration de conseils sur l'utilisation des équipes à partir de dispositifs partagés.</span><span class="sxs-lookup"><span data-stu-id="0fb6d-128">However, these steps are a starting point for building guidance for using Teams from shared devices.</span></span>

## <a name="more-information"></a><span data-ttu-id="0fb6d-129">Plus d'informations</span><span class="sxs-lookup"><span data-stu-id="0fb6d-129">More Information</span></span>

[<span data-ttu-id="0fb6d-130">Bitlocker dans le gestionnaire de configuration</span><span class="sxs-lookup"><span data-stu-id="0fb6d-130">Bitlocker in Configuration Manager</span></span>](https://docs.microsoft.com/mem/configmgr/protect/deploy-use/bitlocker/deploy-management-agent)

[<span data-ttu-id="0fb6d-131">Bitlocker pour Windows 10 dans Intune</span><span class="sxs-lookup"><span data-stu-id="0fb6d-131">Bitlocker for Windows 10 in Intune</span></span>](https://docs.microsoft.com/mem/intune/protect/encrypt-devices)

[<span data-ttu-id="0fb6d-132">Sécurité des terminaux dans Intune</span><span class="sxs-lookup"><span data-stu-id="0fb6d-132">Endpoint security in Intune</span></span>](https://docs.microsoft.com/mem/intune/protect/endpoint-security)

<span data-ttu-id="0fb6d-133">[Activez](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app)l'antivirus Microsoft Defender dans votre sécurité Windows et[lancez des analyses](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#run-a-scan-with-the-windows-security-app)</span><span class="sxs-lookup"><span data-stu-id="0fb6d-133">[Enable](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#ensure-microsoft-defender-antivirus-is-enabled-in-the-windows-security-app) Microsoft Defender Antivirus in your Windows Security and [run scans](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus#run-a-scan-with-the-windows-security-app)</span></span>

[<span data-ttu-id="0fb6d-134"> Article du centre de sécurité Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="0fb6d-134">Microsoft Defender security center article</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus)

[<span data-ttu-id="0fb6d-135"> Client web Teams/application web des équipes </span><span class="sxs-lookup"><span data-stu-id="0fb6d-135">Teams web client/teams web app</span></span>](https://docs.microsoft.com/microsoftteams/get-clients#web-client)

[<span data-ttu-id="0fb6d-136"> Sécurité et Microsoft Team</span><span class="sxs-lookup"><span data-stu-id="0fb6d-136">Security and Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/teams-security-guide)
