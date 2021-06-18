---
title: Déployer le contrôle d’admission des appels dans Skype Entreprise Server
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
ms.assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
description: Le contrôle d’admission des appels (CAC) est une solution qui détermine si une session en temps réel peut être établie en tenant compte de la bande passante disponible pour éviter toute dégradation de la qualité audio/vidéo sur des réseaux saturés.
ms.openlocfilehash: af08afe02b1dc138aa38ded654d567aed6a09247
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49836884"
---
# <a name="deploy-call-admission-control-in-skype-for-business-server"></a>Déployer le contrôle d’admission des appels dans Skype Entreprise Server
 
Le contrôle d’admission des appels (CAC) est une solution qui détermine si une session en temps réel peut être établie en tenant compte de la bande passante disponible pour éviter toute dégradation de la qualité audio/vidéo sur des réseaux saturés. Pour plus d’informations, voir Planifier le contrôle [d’admission des appels dans Skype Entreprise Server.](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)
  
### <a name="to-deploy-call-admission-control"></a>Pour déployer le contrôle d’admission des appels

1.  Rassemblez toutes les informations requises pour votre topologie de réseau d’entreprise, comme décrit dans l’exemple : Collecte des conditions requises pour le contrôle d’admission des appels [dans Skype Entreprise Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).
    
2. Si vous ne l’avez pas déjà fait, vous devez définir des régions et des sites réseau et associer des sous-réseaux à des sites réseau. Pour plus d’informations, voir Déployer des régions réseau, des sites et [des sous-réseaux dans Skype Entreprise.](deploy-network.md)
    
3. Créer des profils de stratégie de bande passante, comme détaillé dans Créer des profils de stratégie [de bande passante dans Skype Entreprise Server](create-bandwidth-policy-profiles.md)
    
4. Créez des liens de région réseau, comme détaillé dans Créer des liens de région [réseau dans Skype Entreprise Server.](create-network-region-links.md)
    
5. Créez des itinéraires inter-régions réseau, comme détaillé dans Créer des [itinéraires interrégion réseau dans Skype Entreprise Server.](create-network-interregional-routes.md)
    
6. Créez des stratégies intersite réseau, comme détaillé dans Créer des [stratégies intersite](create-network-intersite-policies.md)réseau dans Skype Entreprise Server.
    
7. Activez le contrôle d’admission des appels, comme détaillé dans Activer le contrôle [d’admission des appels dans Skype Entreprise Server.](enable-call-admission-control.md)
    
8. Vérifiez quelques paramètres finaux pour vous assurer que tout est correctement installé. Pour plus d’informations, [voir Déploiement du contrôle d’admission des appels : liste de contrôle finale pour Skype Entreprise Server.](final-checklist.md)
    

