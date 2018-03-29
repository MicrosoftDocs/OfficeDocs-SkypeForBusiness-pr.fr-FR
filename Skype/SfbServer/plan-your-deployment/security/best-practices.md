---
title: Recommandations pour votre infrastructure principale dans Skype Entreprise Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
description: Vous avez probablement déjà pris des mesures pour intégrer la tolérance de pannes dans votre système, en utilisant des pratiques telles que la garantie de la redondance matérielle, la prévention de la perte d'alimentation, l'installation régulière des mises à jour, l'établissement des mesures de sécurité antivirus et la surveillance de l'activité du serveur. Ces pratiques bénéficient non seulement votre Skype pour infrastructure de serveur de l’entreprise, mais également l’ensemble du réseau. Si vous n’avez pas implémenté ces pratiques, nous vous recommandons de le faire avant de déployer Skype pour Business Server.
ms.openlocfilehash: 9d79f98ebc66807f21f8d1eef468efc400dd5fbb
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="best-practices-for-your-core-infrastructure-in-skype-for-business-server-2015"></a>Recommandations pour votre infrastructure principale dans Skype Entreprise Server 2015
 
Vous avez probablement déjà pris des mesures pour intégrer la tolérance de pannes dans votre système, en utilisant des pratiques telles que la garantie de la redondance matérielle, la prévention de la perte d'alimentation, l'installation régulière des mises à jour, l'établissement des mesures de sécurité antivirus et la surveillance de l'activité du serveur. Ces pratiques bénéficient non seulement votre Skype pour infrastructure de serveur de l’entreprise, mais également l’ensemble du réseau. Si vous n’avez pas implémenté ces pratiques, nous vous recommandons de le faire avant de déployer Skype pour Business Server.
  
Pour protéger les serveurs de votre Skype pour le déploiement de serveur d’entreprise à partir de dommage accidentel ou délibéré qui peut entraîner un arrêt, prenez les précautions suivantes :
  
- Maintenez vos serveurs à jour avec les mises à jour de sécurité. En vous abonnant au service de notification de sécurité de Microsoft, vous recevez la notification immédiate des bulletins de sécurité pour les produits Microsoft. Pour vous abonner, rendez-vous sur le [site Web du service de notification de sécurité de Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=145202).
    
- Assurez-vous que les droits d'accès sont configurés correctement.
    
- Conservez vos serveurs dans un environnement physique qui empêche l'accès non autorisé. Assurez-vous que le logiciel antivirus adéquat est installé sur tous vos serveurs. Maintenez le logiciel à jour avec les derniers fichiers de signatures de virus. Utilisez la fonction de mise à jour automatique de votre application antivirus pour maintenir à jour les signatures de virus.
    
- Nous vous recommandons de désactiver les services de système d’exploitation Windows Server qui ne sont pas requis sur les ordinateurs sur lesquels vous installez Skype pour Business Server.
    
- Chiffrez les systèmes d'exploitation et les lecteurs de disques où les données sont stockées à l'aide d'un système de chiffrement de volume complet, sauf si vous pouvez garantir un contrôle constant et total des serveurs, l'isolement physique complet et la désaffectation adéquate et sûre des disques remplacés ou défaillants.
    
- Désactivez tous les ports DMA (Direct Memory Access) externes du serveur, sauf si vous pouvez garantir un contrôle très strict de l'accès physique aux serveurs. Les attaques basées sur DMA, qui peuvent être lancées assez facilement, risquent d'exposer des informations très sensibles, telles que les clés de chiffrement privées.
    

