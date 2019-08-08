---
title: Processus de déploiement de l’application d’annonce dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
description: Processus de déploiement et procédure d’annonce d’une application dans Skype entreprise Server Voice.
ms.openlocfilehash: 2edb9364408658e9a164210a9fcd5a0196b10da7
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245310"
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server"></a><span data-ttu-id="2cbfc-103">Processus de déploiement de l’application d’annonce dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="2cbfc-103">Deployment process for the Announcement application in Skype for Business Server</span></span>
 
<span data-ttu-id="2cbfc-104">Processus de déploiement et procédure d’annonce d’une application dans Skype entreprise Server Voice.</span><span class="sxs-lookup"><span data-stu-id="2cbfc-104">Deployment process and steps for Announcement application in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="2cbfc-105">L’application d’annonce est une fonctionnalité voix entreprise qui permet de configurer ce qui arrive aux appels d’extensions non attribuées (extensions valides pour votre organisation, mais qui ne sont pas attribuées à une personne ou à un téléphone).</span><span class="sxs-lookup"><span data-stu-id="2cbfc-105">The Announcement application is an Enterprise Voice feature that enables you to configure what happens to calls to unassigned extensions (extensions that are valid for your organization, but are not assigned to a person or a phone).</span></span> <span data-ttu-id="2cbfc-106">Par exemple, vous pouvez définir que les appels passés à des numéros non attribués doivent déclencher la lecture d’un message et/ou qu’ils doivent être transférés vers une autre destination.</span><span class="sxs-lookup"><span data-stu-id="2cbfc-106">For example, you can configure calls to unassigned numbers to play a message, or to be transferred to a different destination, or both.</span></span>
  
<span data-ttu-id="2cbfc-107">L’application d’annonce est installée en tant que fonctionnalité de l’application de groupe de réponse sur le serveur frontal ou le serveur Standard Edition Server lorsque vous déployez Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="2cbfc-107">The Announcement application is installed as a feature of Response Group application on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="2cbfc-108">Vous devez configurer les annonces en téléchargeant vos fichiers audio ou en configurant la synthèse vocale (TTS) et la table des numéros non attribués.</span><span class="sxs-lookup"><span data-stu-id="2cbfc-108">You need to configure Announcements by uploading your audio files or by configuring text-to-speech (TTS) and configuring the unassigned number table.</span></span>
  
<span data-ttu-id="2cbfc-109">Cette section fournit une vue d’ensemble des étapes de déploiement de l’application d’annonce.</span><span class="sxs-lookup"><span data-stu-id="2cbfc-109">This section provides an overview of the steps involved in deploying the Announcement application.</span></span> <span data-ttu-id="2cbfc-110">Vous devez déployer Enterprise Voice avant de configurer les annonces.</span><span class="sxs-lookup"><span data-stu-id="2cbfc-110">You must deploy Enterprise Voice before you configure announcements.</span></span> <span data-ttu-id="2cbfc-111">Les composants requis par l’application d’annonce sont installés et activés lorsque vous déployez Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="2cbfc-111">The components required by the Announcement application are installed and enabled when you deploy Enterprise Voice.</span></span>
  
<span data-ttu-id="2cbfc-112">**Procédure de déploiement des annonces**</span><span class="sxs-lookup"><span data-stu-id="2cbfc-112">**Announcement Deployment Process**</span></span>

|<span data-ttu-id="2cbfc-113">**Phase**</span><span class="sxs-lookup"><span data-stu-id="2cbfc-113">**Phase**</span></span>|<span data-ttu-id="2cbfc-114">**Étapes**</span><span class="sxs-lookup"><span data-stu-id="2cbfc-114">**Steps**</span></span>|<span data-ttu-id="2cbfc-115">**Rôles**</span><span class="sxs-lookup"><span data-stu-id="2cbfc-115">**Roles**</span></span>|<span data-ttu-id="2cbfc-116">**Documentation de déploiement**</span><span class="sxs-lookup"><span data-stu-id="2cbfc-116">**Deployment documentation**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2cbfc-117">Configurer les paramètres d’annonce</span><span class="sxs-lookup"><span data-stu-id="2cbfc-117">Configure Announcement settings</span></span>  <br/> | <span data-ttu-id="2cbfc-118">Créez l’annonce en enregistrant et en téléchargeant des fichiers audio ou en utilisant la synthèse vocale (TTS).</span><span class="sxs-lookup"><span data-stu-id="2cbfc-118">Create the announcement by recording and uploading audio files or by using text-to-speech (TTS).</span></span> <br/>  <span data-ttu-id="2cbfc-119">Configurez les plages de numéros non attribués dans la table des numéros non attribués et associez-les à l’annonce appropriée.</span><span class="sxs-lookup"><span data-stu-id="2cbfc-119">Configure the unassigned number ranges in the unassigned number table and associate them with the appropriate announcement.</span></span> <br/> |<span data-ttu-id="2cbfc-120">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="2cbfc-120">RTCUniversalServerAdmins</span></span>  <br/> <span data-ttu-id="2cbfc-121">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="2cbfc-121">CsVoiceAdministrator</span></span>  <br/> <span data-ttu-id="2cbfc-122">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="2cbfc-122">CsServerAdministrator</span></span>  <br/> <span data-ttu-id="2cbfc-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="2cbfc-123">CsAdministrator</span></span>  <br/> <span data-ttu-id="2cbfc-124">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="2cbfc-124">CsViewOnlyAdministrator</span></span>  <br/> |[<span data-ttu-id="2cbfc-125">Création ou suppression d’une annonce dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="2cbfc-125">Create or delete an announcement in Skype for Business Server</span></span>](create-an-announcement.md) <br/> [<span data-ttu-id="2cbfc-126">Création ou modification d’une plage de numéros non affectées dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="2cbfc-126">Create or modify an unassigned number range in Skype for Business Server</span></span>](create-or-modify-an-unassigned-number-range.md) <br/> |
|<span data-ttu-id="2cbfc-127">Vérifier le déploiement de votre annonce</span><span class="sxs-lookup"><span data-stu-id="2cbfc-127">Verify your Announcement deployment</span></span>  <br/> |<span data-ttu-id="2cbfc-128">Testez vos annonces en les écoutant afin de vérifier que votre configuration fonctionne comme prévu.</span><span class="sxs-lookup"><span data-stu-id="2cbfc-128">Test by listening to announcements to verify that your configuration works as expected.</span></span>  <br/> |-  <br/> |[<span data-ttu-id="2cbfc-129">Facultatif Vérifier le déploiement d’annonce dans Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="2cbfc-129">(Optional) Verify Announcement deployment in Skype for Business</span></span>](optional-verify-announcement-deployment.md) <br/> |
   

