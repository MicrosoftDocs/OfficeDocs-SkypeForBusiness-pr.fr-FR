---
title: Processus de déploiement de l’application Annonce dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
description: Processus de déploiement et étapes de l’application Annonce dans Skype Entreprise Server Voix Entreprise.
ms.openlocfilehash: cfb1436f22681b45de5c399907d4776a9d1db5de
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812304"
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server"></a><span data-ttu-id="0c6b7-103">Processus de déploiement de l’application Annonce dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="0c6b7-103">Deployment process for the Announcement application in Skype for Business Server</span></span>
 
<span data-ttu-id="0c6b7-104">Processus de déploiement et étapes de l’application Annonce dans Skype Entreprise Server Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="0c6b7-104">Deployment process and steps for Announcement application in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="0c6b7-105">L’application d’annonce est une fonctionnalité Voix Entreprise qui vous permet de configurer ce qu’il advient des appels aux extensions non affectées (extensions valides pour votre organisation, mais qui ne sont pas affectées à une personne ou à un téléphone).</span><span class="sxs-lookup"><span data-stu-id="0c6b7-105">The Announcement application is an Enterprise Voice feature that enables you to configure what happens to calls to unassigned extensions (extensions that are valid for your organization, but are not assigned to a person or a phone).</span></span> <span data-ttu-id="0c6b7-106">Par exemple, vous pouvez définir que les appels passés à des numéros non attribués doivent déclencher la lecture d’un message et/ou qu’ils doivent être transférés vers une autre destination.</span><span class="sxs-lookup"><span data-stu-id="0c6b7-106">For example, you can configure calls to unassigned numbers to play a message, or to be transferred to a different destination, or both.</span></span>
  
<span data-ttu-id="0c6b7-107">L’application Announcement est installée en tant que fonctionnalité de l’application Response Group sur le serveur frontal ou le serveur Standard Edition Server lorsque vous déployez Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="0c6b7-107">The Announcement application is installed as a feature of Response Group application on the Front End Server or Standard Edition server when you deploy Enterprise Voice.</span></span> <span data-ttu-id="0c6b7-108">Vous devez configurer les annonces en téléchargeant vos fichiers audio ou en configurant la synthèse vocale (TTS) et la table des numéros non attribués.</span><span class="sxs-lookup"><span data-stu-id="0c6b7-108">You need to configure Announcements by uploading your audio files or by configuring text-to-speech (TTS) and configuring the unassigned number table.</span></span>
  
<span data-ttu-id="0c6b7-109">Cette section fournit une vue d’ensemble des étapes impliquées dans le déploiement de l’application Annonce.</span><span class="sxs-lookup"><span data-stu-id="0c6b7-109">This section provides an overview of the steps involved in deploying the Announcement application.</span></span> <span data-ttu-id="0c6b7-110">Vous devez déployer Voix Entreprise avant de configurer des annonces.</span><span class="sxs-lookup"><span data-stu-id="0c6b7-110">You must deploy Enterprise Voice before you configure announcements.</span></span> <span data-ttu-id="0c6b7-111">Les composants requis par l’application Annonce sont installés et activés lorsque vous déployez Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="0c6b7-111">The components required by the Announcement application are installed and enabled when you deploy Enterprise Voice.</span></span>
  
<span data-ttu-id="0c6b7-112">**Processus de déploiement des annonces**</span><span class="sxs-lookup"><span data-stu-id="0c6b7-112">**Announcement Deployment Process**</span></span>

|<span data-ttu-id="0c6b7-113">**Étape**</span><span class="sxs-lookup"><span data-stu-id="0c6b7-113">**Phase**</span></span>|<span data-ttu-id="0c6b7-114">**Étapes**</span><span class="sxs-lookup"><span data-stu-id="0c6b7-114">**Steps**</span></span>|<span data-ttu-id="0c6b7-115">**Rôles**</span><span class="sxs-lookup"><span data-stu-id="0c6b7-115">**Roles**</span></span>|<span data-ttu-id="0c6b7-116">**Documentation de déploiement**</span><span class="sxs-lookup"><span data-stu-id="0c6b7-116">**Deployment documentation**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0c6b7-117">Configurer les paramètres d’annonce</span><span class="sxs-lookup"><span data-stu-id="0c6b7-117">Configure Announcement settings</span></span>  <br/> | <span data-ttu-id="0c6b7-118">Créez l’annonce en enregistrant et en téléchargeant des fichiers audio ou en utilisant la synthèse vocale (TTS).</span><span class="sxs-lookup"><span data-stu-id="0c6b7-118">Create the announcement by recording and uploading audio files or by using text-to-speech (TTS).</span></span> <br/>  <span data-ttu-id="0c6b7-119">Configurez les plages de numéros non attribués dans la table des numéros non attribués et associez-les à l’annonce appropriée.</span><span class="sxs-lookup"><span data-stu-id="0c6b7-119">Configure the unassigned number ranges in the unassigned number table and associate them with the appropriate announcement.</span></span> <br/> |<span data-ttu-id="0c6b7-120">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="0c6b7-120">RTCUniversalServerAdmins</span></span>  <br/> <span data-ttu-id="0c6b7-121">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="0c6b7-121">CsVoiceAdministrator</span></span>  <br/> <span data-ttu-id="0c6b7-122">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="0c6b7-122">CsServerAdministrator</span></span>  <br/> <span data-ttu-id="0c6b7-123">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="0c6b7-123">CsAdministrator</span></span>  <br/> <span data-ttu-id="0c6b7-124">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="0c6b7-124">CsViewOnlyAdministrator</span></span>  <br/> |[<span data-ttu-id="0c6b7-125">Créer ou supprimer une annonce dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="0c6b7-125">Create or delete an announcement in Skype for Business Server</span></span>](create-an-announcement.md) <br/> [<span data-ttu-id="0c6b7-126">Création ou modification d’une plage de numéros non signés dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="0c6b7-126">Create or modify an unassigned number range in Skype for Business Server</span></span>](create-or-modify-an-unassigned-number-range.md) <br/> |
|<span data-ttu-id="0c6b7-127">Vérifier le déploiement de votre annonce</span><span class="sxs-lookup"><span data-stu-id="0c6b7-127">Verify your Announcement deployment</span></span>  <br/> |<span data-ttu-id="0c6b7-128">Testez vos annonces en les écoutant afin de vérifier que votre configuration fonctionne comme prévu.</span><span class="sxs-lookup"><span data-stu-id="0c6b7-128">Test by listening to announcements to verify that your configuration works as expected.</span></span>  <br/> |-  <br/> |[<span data-ttu-id="0c6b7-129">(Facultatif) Vérifier le déploiement des annonces dans Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="0c6b7-129">(Optional) Verify Announcement deployment in Skype for Business</span></span>](optional-verify-announcement-deployment.md) <br/> |
   

