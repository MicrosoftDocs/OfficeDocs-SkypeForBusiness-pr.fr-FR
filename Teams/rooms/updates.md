---
title: Gérer Windows mises à jour pour Salles Microsoft Teams
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.assetid: ''
description: Les administrateurs peuvent en savoir plus sur la gestion des mises Windows jour et Windows mises à jour des fonctionnalités pour Salles Microsoft Teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 28f5d9def3a5217d1d34343e27cbaddb6a3433b9
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58602119"
---
# <a name="manage-windows-updates"></a>Gérer Windows mises à jour

Salles Microsoft Teams s’exécute sur Windows 10 Entreprise IoT ou Windows 10 Entreprise (VL) et reçoit les mêmes mises à jour Windows et builds du système d’exploitation que les ordinateurs de bureau standard.

Windows Les mises à jour peuvent être gérées comme expliqué dans les sections suivantes :

## <a name="hands-off-approach"></a>Approche pratique 

- Par défaut, les mises à jour sont téléchargées directement à partir Windows mises à jour automatiquement et installées en dehors des heures d’ouverture.
- Les mises à jour non reportables installent automatiquement le premier jour de la publication.
- Les mises à jour de la qualité et les pilotes sont téléchargés et installés le premier jour automatiquement.
- Mises à jour de fonctionnalités. Consultez les notes qui suivent.

## <a name="windows-updates-for-business-gpo-or-intune"></a>Windows Mises à jour pour les entreprises (GPO ou Intune)  

- [Windows mises à jour pour les entreprises téléchargées](/windows/deployment/update/waas-manage-updates-wufb)
- Les mises à jour sont téléchargées à partir Windows Update ou de votre WSUS, mais avec des retards configurés au-delà de la date de publication d’origine.
- Vous pouvez utiliser plusieurs utils ou stratégies filtrées pour créer des « anneaux » de déploiement où les administrateurs peuvent spécifier les appareils qui installent les mises à jour de qualité en premier et ceux installés ultérieurement. La fiabilité et les performances peuvent être testées sur un sous-ensemble de systèmes avant de déployer les mises à jour dans l’ensemble du déploiement sans avoir à gérer les mises à jour Windows dans Configuration Manager.
- Les mises à jour WSUS et [](/windows/deployment/update/waas-integrate-wufb) Windows Entreprise peuvent être configurées en même temps si vous souhaitez à la fois la gestion de la bande passante et la Windows de mise à jour pour les entreprises.
- Mises à jour de fonctionnalités. Consultez les notes qui suivent.

## <a name="wsusconfiguration-manager"></a>WSUS/Configuration Manager

- [Téléchargement de WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager)
- Tout comme Windows Mise à jour pour les entreprises, mais avec la possibilité de cibler des ko spécifiques à l’intérieur de chaque « anneau » ou du déploiement entier. Chaque mise à jour peut être déployée et testée individuellement à tout moment, plutôt que de s’appuyer sur un certain délai.
- Mises à jour de fonctionnalités. Consultez les notes qui suivent.

### <a name="feature-updates"></a>Mises à jour de fonctionnalités

Contrairement aux mises à jour de qualité et non reportables, Windows 10 « Mises à jour de fonctionnalités » (principales mises à jour du système d’exploitation) ne sera installée qu’après les tests effectués par Microsoft et validera une fonctionnalité de mise à jour avec Salles Microsoft Teams. Même si la mise à jour est publiée pour le canal Semi-Annual (ou ciblée si des systèmes sont destinés à ce canal à des tests) ou poussés manuellement, un appareil Microsoft Room Systems ne permet pas d’installer la mise à jour non testée.

Salles Microsoft Teams « préinstallée » avec une approche pratique et n’installe pas de mise à jour ou de redémarrage automatique d’un appareil Windows pour une mise à jour Windows automatique. Les systèmes téléchargent une mise à jour et attendez le redémarrage suivant pour l’installer. Sauf si quelqu’un le redémarre manuellement, l’installation se produit uniquement au redémarrage nocturne automatique. Windows Les mises à jour doivent être transparentes dans la salle et le fonctionnement normal ne doit jamais être interrompu par Windows mises à jour.

Si vous choisissez d’utiliser des appareils de joint noms de domaine, utilisez Microsoft Endpoint Configuration Manager WSUS. Faites attention aux stratégies ou actions qui entraînent une mise à jour de l’appareil ou un redémarrage forcé pendant les heures d’ouverture. Les systèmes dans votre déploiement ne doivent pas redémarrer pendant l’utilisation ou ne doivent pas être alertés sur les mises à jour Windows de l’interface utilisateur pendant les heures d’utilisation. Si ce comportement se produit, examinez votre configuration.