---
title: Recommandations en matière d’infrastructure principale dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
description: Vous avez probablement déjà pris des mesures pour intégrer la tolérance de pannes dans votre système, en utilisant des pratiques telles que la garantie de la redondance matérielle, la prévention de la perte d'alimentation, l'installation régulière des mises à jour, l'établissement des mesures de sécurité antivirus et la surveillance de l'activité du serveur. Ces pratiques profitent non seulement de votre infrastructure serveur Skype entreprise, mais aussi de votre réseau entier. Si vous n’avez pas implémenté ces pratiques, nous vous conseillons de le faire avant de déployer Skype entreprise Server.
ms.openlocfilehash: c1f6a6ebe31276b8dbcd9037fa373baffc055fde
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296965"
---
# <a name="best-practices-for-your-core-infrastructure-in-skype-for-business-server"></a>Recommandations en matière d’infrastructure principale dans Skype entreprise Server
 
Vous avez probablement déjà pris des mesures pour intégrer la tolérance de pannes dans votre système, en utilisant des pratiques telles que la garantie de la redondance matérielle, la prévention de la perte d'alimentation, l'installation régulière des mises à jour, l'établissement des mesures de sécurité antivirus et la surveillance de l'activité du serveur. Ces pratiques profitent non seulement de votre infrastructure serveur Skype entreprise, mais aussi de votre réseau entier. Si vous n’avez pas implémenté ces pratiques, nous vous conseillons de le faire avant de déployer Skype entreprise Server.
  
Pour vous aider à protéger les serveurs dans votre déploiement de Skype entreprise Server contre les dommages accidentels ou intentionnelles susceptibles d’entraîner un temps d’arrêt, prenez les précautions suivantes:
  
- Maintenez vos serveurs à jour avec les mises à jour de sécurité. En vous abonnant au service de notification de sécurité de Microsoft, vous recevez la notification immédiate des bulletins de sécurité pour les produits Microsoft. Pour vous abonner, accédez au [site Web Microsoft Technical Security notifications](https://go.microsoft.com/fwlink/p/?LinkId=145202).
    
- Assurez-vous que les droits d'accès sont configurés correctement.
    
- Conservez vos serveurs dans un environnement physique qui empêche l'accès non autorisé. Assurez-vous que le logiciel antivirus adéquat est installé sur tous vos serveurs. Maintenez le logiciel à jour avec les derniers fichiers de signatures de virus. Utilisez la fonction de mise à jour automatique de votre application antivirus pour maintenir à jour les signatures de virus.
    
- Nous vous recommandons de désactiver les services du système d’exploitation Windows Server qui ne sont pas nécessaires sur les ordinateurs sur lesquels vous installez Skype entreprise Server.
    
- Chiffrez les systèmes d'exploitation et les lecteurs de disques où les données sont stockées à l'aide d'un système de chiffrement de volume complet, sauf si vous pouvez garantir un contrôle constant et total des serveurs, l'isolement physique complet et la désaffectation adéquate et sûre des disques remplacés ou défaillants.
    
- Désactivez tous les ports DMA (Direct Memory Access) externes du serveur, sauf si vous pouvez garantir un contrôle très strict de l'accès physique aux serveurs. Les attaques basées sur DMA, qui peuvent être lancées assez facilement, risquent d'exposer des informations très sensibles, telles que les clés de chiffrement privées.
    

