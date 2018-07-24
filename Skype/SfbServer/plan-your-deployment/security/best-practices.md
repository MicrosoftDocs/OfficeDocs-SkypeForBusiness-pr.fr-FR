---
title: Meilleures pratiques pour votre infrastructure principale dans Skype pour Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
description: Vous avez probablement déjà pris des mesures pour intégrer la tolérance de pannes dans votre système, en utilisant des pratiques telles que la garantie de la redondance matérielle, la prévention de la perte d'alimentation, l'installation régulière des mises à jour, l'établissement des mesures de sécurité antivirus et la surveillance de l'activité du serveur. Ces pratiques sont bénéfiques non seulement votre Skype pour l’infrastructure de serveur d’entreprise, mais aussi tout votre réseau. Si vous n’avez pas implémenté ces pratiques, nous vous recommandons de le faire avant de déployer Skype pour Business Server.
ms.openlocfilehash: f88461e7563d28dce145d01a9b47a0176ef0d97f
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20996593"
---
# <a name="best-practices-for-your-core-infrastructure-in-skype-for-business-server"></a>Meilleures pratiques pour votre infrastructure principale dans Skype pour Business Server
 
Vous avez probablement déjà pris des mesures pour intégrer la tolérance de pannes dans votre système, en utilisant des pratiques telles que la garantie de la redondance matérielle, la prévention de la perte d'alimentation, l'installation régulière des mises à jour, l'établissement des mesures de sécurité antivirus et la surveillance de l'activité du serveur. Ces pratiques sont bénéfiques non seulement votre Skype pour l’infrastructure de serveur d’entreprise, mais aussi tout votre réseau. Si vous n’avez pas implémenté ces pratiques, nous vous recommandons de le faire avant de déployer Skype pour Business Server.
  
Pour protéger les serveurs de votre Skype pour le déploiement de serveur d’entreprise à partir de dommages accidentels ou intentionnelle pouvant entraîner des temps d’arrêt, prenez les précautions suivantes :
  
- Maintenez vos serveurs à jour avec les mises à jour de sécurité. En vous abonnant au service de notification de sécurité de Microsoft, vous recevez la notification immédiate des bulletins de sécurité pour les produits Microsoft. Pour vous abonner, rendez-vous sur le [site Web du service de notification de sécurité de Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=145202).
    
- Assurez-vous que les droits d'accès sont configurés correctement.
    
- Conservez vos serveurs dans un environnement physique qui empêche l'accès non autorisé. Assurez-vous que le logiciel antivirus adéquat est installé sur tous vos serveurs. Maintenez le logiciel à jour avec les derniers fichiers de signatures de virus. Utilisez la fonction de mise à jour automatique de votre application antivirus pour maintenir à jour les signatures de virus.
    
- Nous vous recommandons de désactiver les services de système d’exploitation Windows Server qui ne sont pas indispensables sur les ordinateurs sur lesquels vous installez Skype pour Business Server.
    
- Chiffrez les systèmes d'exploitation et les lecteurs de disques où les données sont stockées à l'aide d'un système de chiffrement de volume complet, sauf si vous pouvez garantir un contrôle constant et total des serveurs, l'isolement physique complet et la désaffectation adéquate et sûre des disques remplacés ou défaillants.
    
- Désactivez tous les ports DMA (Direct Memory Access) externes du serveur, sauf si vous pouvez garantir un contrôle très strict de l'accès physique aux serveurs. Les attaques basées sur DMA, qui peuvent être lancées assez facilement, risquent d'exposer des informations très sensibles, telles que les clés de chiffrement privées.
    

