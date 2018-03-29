---
title: Procédure de déploiement de l’application Annonce dans Skype Entreprise Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
description: Processus de déploiement et les étapes à suivre pour l’application d’annonce dans Skype pour Business Server Voix Entreprise.
ms.openlocfilehash: 2188faaf80b3caa89acafd7fdf441ab895d11c45
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server-2015"></a>Procédure de déploiement de l’application Annonce dans Skype Entreprise Server 2015
 
Processus de déploiement et les étapes à suivre pour l’application d’annonce dans Skype pour Business Server Voix Entreprise.
  
L’application de l’annonce est une fonctionnalité de Voix Entreprise qui vous permet de configurer ce qui arrive aux appels aux extensions non attribuées (les extensions qui sont valides pour votre organisation, mais qui ne sont pas affectées à une personne ou d’un téléphone). Par exemple, vous pouvez définir que les appels passés à des numéros non attribués doivent déclencher la lecture d’un message et/ou qu’ils doivent être transférés vers une autre destination.
  
L’application de l’annonce est installée comme une fonctionnalité de l’application de groupe de réponse sur le serveur frontal ou Standard Edition serveur lors du déploiement de Voix Entreprise. Vous devez configurer les annonces en téléchargeant vos fichiers audio ou en configurant la synthèse vocale (TTS) et la table des numéros non attribués.
  
Cette section fournit une vue d’ensemble des étapes impliquées dans le déploiement de l’application de l’annonce. Vous devez déployer les Voix Entreprise avant de configurer les annonces. Les composants requis par l’application d’annonce installés et activés lors du déploiement de Voix Entreprise.
  
**Processus de déploiement d’annonce**

|**Phase de**|**Étapes**|**Rôles**|**Documentation sur le déploiement**|
|:-----|:-----|:-----|:-----|
|Configurer les paramètres d’annonce  <br/> | Créez l’annonce en enregistrant et en téléchargeant des fichiers audio ou en utilisant la synthèse vocale (TTS). <br/>  Configurez les plages de numéros non attribués dans la table des numéros non attribués et associez-les à l’annonce appropriée. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsViewOnlyAdministrator  <br/> |[Créer ou supprimer une annonce dans Skype pour Business Server 2015](create-an-announcement.md) <br/> [Créer ou modifier une plage de numéros non attribuée dans Skype pour Business Server 2015](create-or-modify-an-unassigned-number-range.md) <br/> |
|Vérifier le déploiement de votre annonce  <br/> |Testez vos annonces en les écoutant afin de vérifier que votre configuration fonctionne comme prévu.  <br/> |-  <br/> |[(Facultatif) Vérifier le déploiement d’annonce dans Skype pour entreprise 2015](optional-verify-announcement-deployment.md) <br/> |
   

