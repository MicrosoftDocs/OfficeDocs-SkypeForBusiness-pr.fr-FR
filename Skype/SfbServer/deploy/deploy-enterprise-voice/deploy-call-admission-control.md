---
title: Déploiement du contrôle d’admission des appels dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: Le contrôle d’admission des appels (CAC) est une solution qui détermine si une session en temps réel peut être établie en tenant compte de la bande passante disponible pour éviter toute dégradation de la qualité audio/vidéo sur des réseaux saturés. Pour plus d’informations, voir Plan pour le contrôle d’admission des appels dans Skype for Business Server 2015.
ms.openlocfilehash: 471bc7abe8a79f2ef4b4cc322450dbc7c639129f
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="deploy-call-admission-control-in-skype-for-business-server-2015"></a>Déploiement du contrôle d’admission des appels dans Skype Entreprise Server 2015
 
Le contrôle d’admission des appels (CAC) est une solution qui détermine si une session en temps réel peut être établie en tenant compte de la bande passante disponible pour éviter toute dégradation de la qualité audio/vidéo sur des réseaux saturés. Pour plus d’informations, voir [planifier le contrôle d’admission des appels d’appel dans Skype pour Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).
  
### <a name="to-deploy-call-admission-control"></a>Pour déployer le contrôle d’admission des appels

1.  Rassembler toutes les informations requises pour la topologie de votre réseau d’entreprise, comme décrit dans [exemple : collecte des conditions requises pour le contrôle d’admission des appels dans Skype pour Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).
    
2. Si ce n’est déjà fait, vous devez définir des régions et des sites réseau et associer les sous-réseaux à des sites réseau. Pour plus d’informations, voir [déployer les régions de réseau, des sites et sous-réseaux de Skype pour Business 2015](deploy-network.md).
    
3. Créer des profils de stratégie, comme indiqué dans [créer des profils de stratégie de bande passante dans Skype pour Business Server 2015](create-bandwidth-policy-profiles.md) de bande passante
    
4. Créer des liens de région réseau, comme indiqué dans [créer des liens de région réseau dans Skype pour Business Server 2015](create-network-region-links.md).
    
5. Créez des itinéraires réseau entre les zones, comme indiqué dans [créer des itinéraires réseau interrégional dans Skype pour Business Server 2015](create-network-interregional-routes.md).
    
6. Créer des stratégies inter-sites réseau, comme indiqué dans [créer des stratégies inter-sites réseau dans Skype pour Business Server 2015](create-network-intersite-policies.md).
    
7. Activer le contrôle d’admission des appels, comme indiqué dans [le contrôle d’admission des appels d’appel activer dans Skype pour Business Server 2015](enable-call-admission-control.md).
    
8. Vérifiez quelques derniers paramètres pour vous assurer que tout est configuré correctement. Pour plus d’informations, voir [déploiement du contrôle d’admission des appels : liste de vérification finale pour Skype pour Business Server 2015](final-checklist.md).
    

