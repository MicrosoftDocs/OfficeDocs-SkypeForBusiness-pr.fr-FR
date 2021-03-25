---
title: Gérer les mises à jour Windows pour les salles Microsoft Teams
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: ''
description: Les administrateurs peuvent en savoir plus sur la gestion des mises à jour de Windows Update et des mises à jour des fonctionnalités Windows pour les salles Microsoft Teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c7bb233ceedadeaf9c7f14ddf831bd9d324d9211
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117362"
---
# <a name="manage-windows-updates"></a>Gérer les mises à jour Windows

Les salles Microsoft Teams s’exécutent sur Windows 10 Entreprise IoT ou Windows 10 Entreprise (VL) et reçoivent les mêmes mises à jour Windows et les mêmes builds de système d’exploitation qu’un ordinateur de bureau standard.

Les mises à jour Windows peuvent être gérées comme expliqué dans les sections suivantes :

## <a name="hands-off-approach"></a>Approche pratique 

- Par défaut, les mises à jour sont téléchargées directement à partir de Windows Update automatiquement et installées en dehors des heures d’ouverture.
- Les mises à jour non reportables installent automatiquement le premier jour de la publication.
- Les mises à jour de la qualité et les pilotes sont téléchargés et installés le premier jour automatiquement.
- Mises à jour de fonctionnalités. Consultez les notes qui suivent.

## <a name="windows-updates-for-business-gpo-or-intune"></a>Windows Updates for Business (GPO ou Intune)  

- [Téléchargement de Windows Updates for Business](/windows/deployment/update/waas-manage-updates-wufb)
- Les mises à jour sont téléchargées à partir de Windows Update ou de votre appareil WSUS, mais avec des retards configurés au-delà de la date de publication d’origine.
- Vous pouvez utiliser plusieurs utils ou stratégies filtrées pour créer des « anneaux » de déploiement où les administrateurs peuvent spécifier les appareils qui installent les mises à jour de qualité en premier et ceux qui seront installés ultérieurement. La fiabilité et les performances peuvent être testées sur un sous-ensemble de systèmes avant de déployer les mises à jour dans l’ensemble du déploiement sans que cela ne se passe par la gestion des mises à jour Windows dans Configuration Manager.
- WSUS et Windows Updates [](/windows/deployment/update/waas-integrate-wufb) for Business peuvent être configurés en même temps si vous souhaitez à la fois la gestion de la bande passante et le contrôle de Windows Updates for Business.
- Mises à jour de fonctionnalités. Consultez les notes qui suivent.

## <a name="wsusconfiguration-manager"></a>WSUS/Configuration Manager

- [Téléchargement de WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager)
- Tout comme Windows Update for Business, mais avec l’option supplémentaire de cibler des Ko spécifiques à l’intérieur de chaque « anneau » ou du déploiement entier. Chaque mise à jour peut être déployée et testée individuellement à tout moment, plutôt que de s’appuyer sur un certain délai.
- Mises à jour de fonctionnalités. Consultez les notes qui suivent.

### <a name="feature-updates"></a>Mises à jour de fonctionnalités

Contrairement aux mises à jour de qualité et non reportables, les « mises à jour de fonctionnalités » Windows 10 (principales mises à jour du système d’exploitation) ne seront installées qu’après les tests de Microsoft et valideront une fonctionnalité de mise à jour donnée avec les salles Microsoft Teams. Même si la mise à jour est publiée pour le canal Semi-Annual (ou ciblée si des systèmes sont destinés à ce canal à des tests) ou poussés manuellement, un appareil Microsoft Room Systems ne permet pas d’installer la mise à jour non testée.

Les salles Microsoft Teams fonctionnent « préinstallées » avec une approche pratique et ne peuvent pas installer Windows Update ou redémarrer automatiquement un appareil pour une mise à jour Windows. Les systèmes téléchargent une mise à jour et attendez le redémarrage suivant pour l’installer. Sauf si quelqu’un le redémarre manuellement, l’installation se produit uniquement au redémarrage nocturne automatique. Les mises à jour Windows doivent être transparentes dans la salle et le fonctionnement normal ne doit jamais être interrompu par Windows Update.

Si vous choisissez d’utiliser des appareils de jointation de domaine, utilisez Microsoft Endpoint Configuration Manager ou WSUS. Prêter une attention particulière aux stratégies ou actions qui entraînent une mise à jour de l’appareil ou un redémarrage forcé pendant les heures d’ouverture. Les systèmes dans votre déploiement ne doivent pas redémarrer pendant l’utilisation ou ne doivent pas être alertés sur les mises à jour Windows pendant les heures d’utilisation. Dans ce cas, examinez votre configuration.