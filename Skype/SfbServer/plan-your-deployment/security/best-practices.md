---
title: Meilleures pratiques pour votre infrastructure principale dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
description: Vous avez probablement déjà pris des mesures afin d’intégrer la tolérance de panne dans votre système, en utilisant diverses pratiques courantes telles que la mise en place d’une redondance au niveau du matériel, la protection contre les coupures de courant, l’installation régulière de mises à jour de sécurité, l’utilisation d’antivirus et le contrôle de l’activité du serveur. Ces pratiques bénéficient non seulement à votre infrastructure Skype Entreprise Server, mais également à l’ensemble de votre réseau. Si vous n’avez pas implémenté ces pratiques, nous vous recommandons de le faire avant de déployer Skype Entreprise Server.
ms.openlocfilehash: 352541cf2dfa91eef24f09c4aebd2788c589a10f
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60860941"
---
# <a name="best-practices-for-your-core-infrastructure-in-skype-for-business-server"></a>Meilleures pratiques pour votre infrastructure principale dans Skype Entreprise Server
 
Vous avez probablement déjà pris des mesures afin d’intégrer la tolérance de panne dans votre système, en utilisant diverses pratiques courantes telles que la mise en place d’une redondance au niveau du matériel, la protection contre les coupures de courant, l’installation régulière de mises à jour de sécurité, l’utilisation d’antivirus et le contrôle de l’activité du serveur. Ces pratiques bénéficient non seulement à votre infrastructure Skype Entreprise Server, mais également à l’ensemble de votre réseau. Si vous n’avez pas implémenté ces pratiques, nous vous recommandons de le faire avant de déployer Skype Entreprise Server.
  
Pour protéger les serveurs de votre déploiement Skype Entreprise Server contre les dommages accidentels ou intentionnables qui peuvent entraîner un temps d’arrêt, prenez les précautions suivantes :
  
- Mettez régulièrement à jour vos serveurs en installant les mises à jour de sécurité. La souscription d’un abonnement au service de notification de sécurité de Microsoft permet de recevoir une notification immédiate des mises à jour de sécurité pour un produit Microsoft. Pour vous abonner, go to the [Microsoft Technical Security Notifications website](https://go.microsoft.com/fwlink/p/?LinkId=145202).
    
- Vérifiez que les droits d’accès sont correctement configurés.
    
- Installez vos serveurs dans un environnement physique protégé contre les accès non autorisés. Vérifiez que les logiciels antivirus appropriés sont installés sur tous vos serveurs. Mettez à jour ces logiciels à l’aide des fichiers de signatures de virus les plus récents. Utilisez la fonction de mise à jour automatique de vos logiciels antivirus pour mettre à jour vos signatures de virus.
    
- Nous vous recommandons de désactiver les services de système d’exploitation Windows Server qui ne sont pas requis sur les ordinateurs sur Skype Entreprise Server.
    
- Chiffrez les systèmes d’exploitation et les lecteurs de disques où les données sont stockées avec un système de chiffrement de volume complet, à moins que vous puissiez garantir un contrôle constant et total des serveurs, un isolement physique total, ainsi qu’une désaffectation en bonne et due forme des disques remplacés ou en échec.
    
- Désactivez tous les ports DMA (Direct Memory Access) externes du serveur, sauf si vous pouvez garantir un contrôle très serré de l’accès aux serveurs. Les attaques basées sur DMA, qui peuvent être initiées assez facilement, peuvent exposer des informations très sensibles, telles que des clés de chiffrement privées.
    

