---
title: Déploiement du contrôle d’admission des appels dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: Le contrôle d’admission des appels (CAC) est une solution qui détermine si une session en temps réel peut être établie en tenant compte de la bande passante disponible pour éviter toute dégradation de la qualité audio/vidéo sur des réseaux saturés. Pour plus d’informations, voir Plan d’appel de contrôle d’admission dans Skype pour Business Server 2015.
ms.openlocfilehash: 0302663546a099e682b5dc405625d4519fe998d9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-call-admission-control-in-skype-for-business-server-2015"></a>Déploiement du contrôle d’admission des appels dans Skype Entreprise Server 2015
 
Le contrôle d’admission des appels (CAC) est une solution qui détermine si une session en temps réel peut être établie en tenant compte de la bande passante disponible pour éviter toute dégradation de la qualité audio/vidéo sur des réseaux saturés. Pour plus d’informations, consultez le [Plan d’appel de contrôle d’admission dans Skype pour Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).
  
### <a name="to-deploy-call-admission-control"></a>Pour déployer le contrôle d’admission des appels

1.  Rassembler toutes les informations requises pour la topologie de votre réseau d’entreprise, comme décrit dans [exemple : collecte des besoins pour un appel de contrôle d’admission dans Skype pour Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).
    
2. Si ce n’est déjà fait, vous devez définir des régions et des sites réseau et associer les sous-réseaux à des sites réseau. Pour plus d’informations, consultez [zones de réseau de déployer, des sites et des sous-réseaux dans Skype pour entreprise 2015](deploy-network.md).
    
3. Créer des profils de stratégie, comme détaillé dans la [création des profils de stratégie de bande passante dans Skype pour Business Server 2015](create-bandwidth-policy-profiles.md) de la bande passante
    
4. Créer des liens de la région de réseau, comme détaillé dans la [Création de liens de région réseau dans Skype pour Business Server 2015](create-network-region-links.md).
    
5. Créer des itinéraires inter-REGIONALE réseau, comme détaillé dans les [gammes interrégional de réseau créer dans Skype pour Business Server 2015](create-network-interregional-routes.md).
    
6. Créer des stratégies de réseau intersite, comme détaillé dans [créer les stratégies réseau intersites dans Skype pour Business Server 2015](create-network-intersite-policies.md).
    
7. Activer l’appel de contrôle d’admission, comme détaillé dans le [contrôle d’admission activer appel dans Skype pour Business Server 2015](enable-call-admission-control.md).
    
8. Vérifiez quelques derniers paramètres pour vous assurer que tout est configuré correctement. Pour plus d’informations, consultez [appeler le déploiement de contrôle d’admission : liste de vérification finale pour Skype pour Business Server 2015](final-checklist.md).
    

