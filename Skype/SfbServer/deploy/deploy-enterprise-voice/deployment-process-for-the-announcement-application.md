---
title: Processus de déploiement de l’application d’annonce dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
description: Processus de déploiement et procédure d’annonce d’une application dans Skype entreprise Server Voice.
ms.openlocfilehash: 77d15c4ce749a97ec11ed5d5e083ccf6fa2aecfa
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275607"
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server"></a>Processus de déploiement de l’application d’annonce dans Skype entreprise Server
 
Processus de déploiement et procédure d’annonce d’une application dans Skype entreprise Server Voice.
  
L’application d’annonce est une fonctionnalité voix entreprise qui permet de configurer ce qui arrive aux appels d’extensions non attribuées (extensions valides pour votre organisation, mais qui ne sont pas attribuées à une personne ou à un téléphone). Par exemple, vous pouvez définir que les appels passés à des numéros non attribués doivent déclencher la lecture d’un message et/ou qu’ils doivent être transférés vers une autre destination.
  
L’application d’annonce est installée en tant que fonctionnalité de l’application de groupe de réponse sur le serveur frontal ou le serveur Standard Edition Server lorsque vous déployez Enterprise Voice. Vous devez configurer les annonces en téléchargeant vos fichiers audio ou en configurant la synthèse vocale (TTS) et la table des numéros non attribués.
  
Cette section fournit une vue d’ensemble des étapes de déploiement de l’application d’annonce. Vous devez déployer Enterprise Voice avant de configurer les annonces. Les composants requis par l’application d’annonce sont installés et activés lorsque vous déployez Enterprise Voice.
  
**Procédure de déploiement des annonces**

|**Phase**|**Étapes**|**Rôles**|**Documentation de déploiement**|
|:-----|:-----|:-----|:-----|
|Configurer les paramètres d’annonce  <br/> | Créez l’annonce en enregistrant et en téléchargeant des fichiers audio ou en utilisant la synthèse vocale (TTS). <br/>  Configurez les plages de numéros non attribués dans la table des numéros non attribués et associez-les à l’annonce appropriée. <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsViewOnlyAdministrator  <br/> |[Création ou suppression d’une annonce dans Skype entreprise Server](create-an-announcement.md) <br/> [Création ou modification d’une plage de numéros non affectées dans Skype entreprise Server](create-or-modify-an-unassigned-number-range.md) <br/> |
|Vérifier le déploiement de votre annonce  <br/> |Testez vos annonces en les écoutant afin de vérifier que votre configuration fonctionne comme prévu.  <br/> |-  <br/> |[Facultatif Vérifier le déploiement d’annonce dans Skype entreprise](optional-verify-announcement-deployment.md) <br/> |
   

