---
title: Déployer le contrôle d’admission des appels dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 2e41d5a26e99c482041fb29e204f777a6c1a7cd7
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767667"
---
# <a name="deploy-call-admission-control-in-skype-for-business-server"></a>Déployer le contrôle d’admission des appels dans Skype entreprise Server
 
Le contrôle d’admission des appels (CAC) est une solution qui détermine si une session en temps réel peut être établie en tenant compte de la bande passante disponible pour éviter toute dégradation de la qualité audio/vidéo sur des réseaux saturés. Pour plus d’informations, reportez-vous à la section [planifier le contrôle d’admission des appels dans Skype entreprise Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).
  
### <a name="to-deploy-call-admission-control"></a>Pour déployer le contrôle d’admission des appels

1.  Collectez toutes les informations requises pour la topologie de votre réseau d’entreprise, comme décrit dans l' [exemple ci-dessous : rassemblement des exigences de contrôle d’admission des appels dans Skype entreprise Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).
    
2. Si ce n’est déjà fait, vous devez définir des régions et des sites réseau et associer les sous-réseaux à des sites réseau. Pour plus d’informations, reportez-vous à la rubrique [déploiement de régions, de sites et de sous-réseaux dans Skype entreprise](deploy-network.md).
    
3. Créer des profils de stratégie de bande passante, comme détaillé dans [créer des profils de stratégie de bande passante dans Skype entreprise Server](create-bandwidth-policy-profiles.md)
    
4. Créez des liens vers les régions de réseau, comme détaillé dans [créer des liens de région réseau dans Skype entreprise Server](create-network-region-links.md).
    
5. Créez des itinéraires réseau inter-régions, comme détaillé dans [créer des itinéraires réseau interrégionals dans Skype entreprise Server](create-network-interregional-routes.md).
    
6. Créez des stratégies d’intersite réseau, comme décrit dans la [création de stratégies d’intersite réseau dans Skype entreprise Server](create-network-intersite-policies.md).
    
7. Activez le contrôle d’admission des appels, comme indiqué dans la procédure [activer le contrôle d’admission des appels de Skype entreprise Server](enable-call-admission-control.md).
    
8. Vérifiez quelques derniers paramètres pour vous assurer que tout est configuré correctement. Pour plus d’informations, reportez-vous à la rubrique [déploiement de contrôle d’admission des appels : liste de vérification finale pour Skype entreprise Server](final-checklist.md).
    

