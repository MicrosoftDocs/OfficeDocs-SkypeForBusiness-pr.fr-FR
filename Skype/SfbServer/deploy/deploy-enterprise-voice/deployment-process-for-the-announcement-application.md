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
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server"></a>Processus de déploiement de l’application Annonce dans Skype Entreprise Server
 
Processus de déploiement et étapes de l’application Annonce dans Skype Entreprise Server Voix Entreprise.
  
L’application d’annonce est une fonctionnalité Voix Entreprise qui vous permet de configurer ce qu’il advient des appels aux extensions non affectées (extensions valides pour votre organisation, mais qui ne sont pas affectées à une personne ou à un téléphone). Par exemple, vous pouvez définir que les appels passés à des numéros non attribués doivent déclencher la lecture d’un message et/ou qu’ils doivent être transférés vers une autre destination.
  
L’application Announcement est installée en tant que fonctionnalité de l’application Response Group sur le serveur frontal ou le serveur Standard Edition Server lorsque vous déployez Voix Entreprise. Vous devez configurer les annonces en téléchargeant vos fichiers audio ou en configurant la synthèse vocale (TTS) et la table des numéros non attribués.
  
Cette section fournit une vue d’ensemble des étapes impliquées dans le déploiement de l’application Annonce. Vous devez déployer Voix Entreprise avant de configurer des annonces. Les composants requis par l’application Annonce sont installés et activés lorsque vous déployez Voix Entreprise.
  
**Processus de déploiement des annonces**

|**Étape**|**Étapes**|**Rôles**|**Documentation de déploiement**|
|:-----|:-----|:-----|:-----|
|Configurer les paramètres d’annonce  <br/> | Créez l’annonce en enregistrant et en téléchargeant des fichiers audio ou en utilisant la synthèse vocale (TTS). <br/>  Configurez les plages de numéros non attribués dans la table des numéros non attribués et associez-les à l’annonce appropriée. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsViewOnlyAdministrator  <br/> |[Créer ou supprimer une annonce dans Skype Entreprise Server](create-an-announcement.md) <br/> [Création ou modification d’une plage de numéros non signés dans Skype Entreprise Server](create-or-modify-an-unassigned-number-range.md) <br/> |
|Vérifier le déploiement de votre annonce  <br/> |Testez vos annonces en les écoutant afin de vérifier que votre configuration fonctionne comme prévu.  <br/> |-  <br/> |[(Facultatif) Vérifier le déploiement des annonces dans Skype Entreprise](optional-verify-announcement-deployment.md) <br/> |
   

