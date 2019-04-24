---
title: Déployer le contrôle d’admission des appels d’appel dans Skype pour Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: Le contrôle d’admission des appels (CAC) est une solution qui détermine si une session en temps réel peut être établie en tenant compte de la bande passante disponible pour éviter toute dégradation de la qualité audio/vidéo sur des réseaux saturés.
ms.openlocfilehash: 52fcedaab781e9ed76222afb32b56840a3b07c1c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32223140"
---
# <a name="deploy-call-admission-control-in-skype-for-business-server"></a>Déployer le contrôle d’admission des appels d’appel dans Skype pour Business Server
 
Le contrôle d’admission des appels (CAC) est une solution qui détermine si une session en temps réel peut être établie en tenant compte de la bande passante disponible pour éviter toute dégradation de la qualité audio/vidéo sur des réseaux saturés. Pour plus d’informations, voir [planifier le contrôle d’admission des appels d’appel dans Skype pour Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).
  
### <a name="to-deploy-call-admission-control"></a>Pour déployer le contrôle d’admission des appels

1.  Rassembler toutes les informations requises pour la topologie de votre réseau d’entreprise, comme décrit dans [exemple : collecte des conditions requises pour le contrôle d’admission des appels dans Skype pour Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).
    
2. Si ce n’est déjà fait, vous devez définir des régions et des sites réseau et associer les sous-réseaux à des sites réseau. Pour plus d’informations, voir [déployer les régions de réseau, des sites et sous-réseaux de Skype pour les entreprises](deploy-network.md).
    
3. Créer des profils de stratégie, comme indiqué dans [créer des profils de stratégie de bande passante dans Skype pour Business Server](create-bandwidth-policy-profiles.md) de bande passante
    
4. Créer des liens de région réseau, comme indiqué dans [créer des liens de région réseau dans Skype pour Business Server](create-network-region-links.md).
    
5. Créez des itinéraires réseau entre les zones, comme indiqué dans [créer des itinéraires réseau interrégional dans Skype pour Business Server](create-network-interregional-routes.md).
    
6. Créer des stratégies inter-sites réseau, comme indiqué dans [créer des stratégies inter-sites réseau dans Skype pour Business Server](create-network-intersite-policies.md).
    
7. Activer le contrôle d’admission des appels, comme indiqué dans [le contrôle d’admission des appels d’appel activer dans Skype pour Business Server](enable-call-admission-control.md).
    
8. Vérifiez quelques derniers paramètres pour vous assurer que tout est configuré correctement. Pour plus d’informations, voir [déploiement du contrôle d’admission des appels : liste de vérification finale pour Skype pour Business Server](final-checklist.md).
    

