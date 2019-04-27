---
title: Gérer les mises à jour Windows pour les équipes Microsoft salles
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 10/10/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: M365-voice
ms.assetid: ''
description: Gérer les mises à jour Windows pour les équipes Microsoft salles
ms.openlocfilehash: 723ecf20fb835a3d942270e9de6d59416a9cd14a
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2019
ms.locfileid: "33362745"
---
# <a name="manage-windows-updates"></a>Gérer les mises à jour Windows

Salles d’équipes Microsoft s’exécute sur Windows 10 entreprise IoT ou entreprise de 10 Windows (VL) et reçoit les même versions mises à jour Windows et du système d’exploitation de bureau standard.

Mises à jour Windows peut être géré de différentes manières :

## <a name="hands-off-approach"></a>Approche sans intervention 
- Mises à jour peuvent être téléchargés directement à partir de mises à jour automatiquement et installés pendant les heures creuses. Si aucune modification n’est apportée à la configuration Ceci est l’état par défaut.
- Mises à jour peut être différée-non installera automatiquement jour-1 de la version. 
- Qualité des mises à jour et des pilotes de télécharger et installer le premier jour automatiquement. 
- Mises à jour de la fonctionnalité. Voir les remarques supplémentaires ci-dessous. 

## <a name="windows-updates-for-businesshttpsdocsmicrosoftcomwindowsdeploymentupdatewaas-manage-updates-wufb-gpo-or-intune"></a>[Mises à jour de Windows pour les entreprises](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb) (Stratégie de groupe ou Intune)   
- Mises à jour sont téléchargées à partir de Windows Update ou votre WSUS, mais avec des retards configurés après la date de publication d’origine de la base de connaissances. 
- Combinée à plusieurs unités d’organisation ou filtrée des stratégies, il permet la création de déploiement « sonne », où les administrateurs peuvent spécifier quels appareils installez d’abord les mises à jour de la qualité et qui ceux installe ultérieurement. Ainsi, la fiabilité et les performances test sur un sous-ensemble de systèmes avant de déployer des mises à jour sur l’ensemble du déploiement sans la charge de la gestion des mises à jour dans SCCM par exemple.
- WSUS et mises à jour de Windows pour les entreprises peuvent être [configuré en même temps](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb) si vous le souhaitez à la fois gestion de bande passante et le contrôle des mises à jour Windows pour les entreprises fournit.
- Mises à jour de la fonctionnalité. Voir les remarques supplémentaires ci-dessous.

## <a name="wsussccmhttpsdocsmicrosoftcomwindowsdeploymentupdatewaas-manage-updates-configuration-manager"></a>[WSUS/SCCM](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)
- Comme Windows Update pour les entreprises, mais avec l’option supplémentaire de ciblage spécifique Ko dans chaque « anneau » ou la totalité du déploiement. Chaque mise à jour peut être individuellement déployés et testée à volonté, plutôt que d’utiliser sur un retard seulement. 
- Mises à jour de la fonctionnalité. Voir les remarques supplémentaires ci-dessous.


### <a name="feature-updates"></a>Mises à jour de la fonctionnalité

Contrairement à la qualité et Non-Deferable mises à jour Windows 10 « Fonctionnalité des mises à jour » (versions majeures du système d’exploitation) sera installé uniquement une fois que Microsoft teste et valide une fonctionnalité donnée de mises à jour des espaces d’équipes Microsoft. Même s’il est publié à canal annuel séparées (ou cibles si vous avez des systèmes défini sur ce canal de test) ou même manuellement poussée par votre propre tentatives ou les configurations, il ne permet pas l’installation jusqu'à ce que le bloc de fin est supprimé.

Salle d’équipes Microsoft « out-of-box », à l’aide de l’approche, mains ne sera pas installer une mise à jour Windows ou redémarrer un appareil automatiquement en raison d’une mise à jour de Windows. Toutefois, les systèmes peuvent télécharger une mise à jour et attendre le prochain redémarrage de l’installer. Sauf si une personne redémarre manuellement, installation doit se produire lors du redémarrage nocturne automatique. Mises à jour Windows doit être transparent dans la salle, l’interface utilisateur ne doit jamais être interrompu par des mises à jour Windows.

Si vous choisissez de jonction de domaine, utilisez SCCM ou WSUS et prêtez une attention particulière aux stratégies ou les actions qui peuvent conduire à l’appareil de l’installation d’une mise à jour ou de forcer un redémarrage pendant les heures ouvrées. Si vous avez des systèmes de votre déploiement redémarrage lors de l’utilisation ou d’une alerte sur les mises à jour via l’interface utilisateur, vous devez rechercher dans votre configuration.