---
title: Processus de déploiement pour l’application d’annonce dans Skype pour Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
description: Processus de déploiement et les étapes de l’application d’annonce dans Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: 96925df57a36373ee6f031b953f1933b3bac5681
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32223040"
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server"></a>Processus de déploiement pour l’application d’annonce dans Skype pour Business Server
 
Processus de déploiement et les étapes de l’application d’annonce dans Skype pour Business Server Enterprise Voice.
  
L’application d’annonce est une fonctionnalité de voix entreprise qui vous permet de configurer ce qui se passe pour les appels vers les extensions non attribuées (extensions qui sont valides pour votre organisation, mais ne sont pas affectées à une personne ou un téléphone). Par exemple, vous pouvez définir que les appels passés à des numéros non attribués doivent déclencher la lecture d’un message et/ou qu’ils doivent être transférés vers une autre destination.
  
L’application d’annonce est installée en tant que fonctionnalité de l’application Response Group sur le serveur frontal ou Standard Edition server lors du déploiement d’Enterprise Voice. Vous devez configurer les annonces en téléchargeant vos fichiers audio ou en configurant la synthèse vocale (TTS) et la table des numéros non attribués.
  
Cette section fournit une vue d’ensemble des étapes impliquées dans le déploiement de l’application d’annonce. Vous devez déployer Enterprise Voice avant de configurer des annonces. Les composants requis par l’application d’annonce sont installés et activés lors du déploiement d’Enterprise Voice.
  
**Procédure de déploiement des annonces**

|**Phase**|**Étapes**|**Rôles**|**Documentation de déploiement**|
|:-----|:-----|:-----|:-----|
|Configurer les paramètres d’annonce  <br/> | Créez l’annonce en enregistrant et en téléchargeant des fichiers audio ou en utilisant la synthèse vocale (TTS). <br/>  Configurez les plages de numéros non attribués dans la table des numéros non attribués et associez-les à l’annonce appropriée. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsViewOnlyAdministrator  <br/> |[Créer ou supprimer une annonce dans Skype pour Business Server](create-an-announcement.md) <br/> [Créer ou modifier une plage de numéros non attribuée dans Skype pour Business Server](create-or-modify-an-unassigned-number-range.md) <br/> |
|Vérifier le déploiement de votre annonce  <br/> |Testez vos annonces en les écoutant afin de vérifier que votre configuration fonctionne comme prévu.  <br/> |-  <br/> |[(Facultatif) Vérifier le déploiement des annonces dans Skype pour les entreprises](optional-verify-announcement-deployment.md) <br/> |
   

