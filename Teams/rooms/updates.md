---
title: Gérer Windows mises à jour pour Salles Microsoft Teams
ms.author: czawideh
author: cazawideh
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
description: Les administrateurs peuvent en savoir plus sur la gestion des mises Windows jour et Windows fonctionnalités pour les utilisateurs Salles Microsoft Teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 95b99e8869ed9fa63a372c6c40d1d0d2be28c019
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503751"
---
# <a name="manage-windows-updates"></a>Gérer Windows mises à jour

Salles Microsoft Teams s’exécute sur Windows 10 Entreprise IoT ou Windows 10 Entreprise (VL) et reçoit les mêmes mises à Windows et builds du système d’exploitation que les ordinateurs de bureau standard.

Windows mises à jour peuvent être gérées comme expliqué dans les sections suivantes :

## <a name="hands-off-approach"></a>Approche pratique 

- Par défaut, les mises à jour sont téléchargées directement à partir Windows mises à jour automatiquement et installées en dehors des heures d’ouverture.
- Les mises à jour non reportables installent automatiquement le jour de la publication.
- Les mises à jour de la qualité et les pilotes sont téléchargés et installés automatiquement le premier jour.
- Mises à jour de fonctionnalités. Consultez les notes qui suivent.

## <a name="windows-updates-for-business-gpo-or-intune"></a>Windows mises à jour pour les entreprises (GPO ou Intune)  

- [Windows mises à jour pour les entreprises téléchargées](/windows/deployment/update/waas-manage-updates-wufb)
- Les mises à jour sont téléchargées à partir de Windows Update ou de votre Windows Server Update Services (WSUS), mais avec des retards configurés au-delà de la date de publication d’origine.
- Vous pouvez utiliser plusieurs utils ou stratégies filtrées pour créer des « anneaux » de déploiement où les administrateurs peuvent spécifier les appareils salles Teams installer d’abord les mises à jour de qualité et ceux qui seront installés ultérieurement. La fiabilité et les performances peuvent être testées sur un sous-ensemble d’appareils avant de déployer les mises à jour dans l’ensemble du déploiement sans avoir à gérer les mises à jour Windows configuration manager.
- Les mises à jour WSUS et Windows Entreprise peuvent être configurées [](/windows/deployment/update/waas-integrate-wufb) en même temps si vous souhaitez à la fois la gestion de la bande passante et le contrôle des mises à jour Windows entreprise.
- Mises à jour de fonctionnalités. Consultez les notes qui suivent.

## <a name="wsusconfiguration-manager"></a>WSUS/Configuration Manager

- [Téléchargement de WSUS/Configuration Manager](/windows/deployment/update/waas-manage-updates-configuration-manager)
- Tout comme Windows Mise à jour pour les entreprises, mais avec la possibilité de cibler des ko spécifiques à l’intérieur de chaque « anneau » ou du déploiement entier. Chaque mise à jour peut être déployée et testée individuellement à tout moment, plutôt que de s’appuyer sur un certain délai.
- Mises à jour de fonctionnalités. Consultez les notes qui suivent.

### <a name="feature-updates"></a>Mises à jour de fonctionnalités

Contrairement aux mises à jour de qualité et non reportables, Windows 10 « Mises à jour de fonctionnalités » (principales mises à jour du système d’exploitation) ne sera installée qu’après les tests effectués par Microsoft et validera une fonctionnalité de mise à jour avec Salles Microsoft Teams. Même si la mise à jour est publiée pour le canal Semi-Annual (ou ciblée si des systèmes sont destinés à ce canal à des tests) ou poussés manuellement, Salles Microsoft Teams ne permet pas d’installer la mise à jour non testée.

Salles Microsoft Teams « pré-boîte » avec une approche pratique. salles Teams télécharger une mise à jour et attendre le redémarrage suivant pour l’installer. Sauf si quelqu’un le redémarre manuellement, l’installation se produit uniquement au redémarrage nocturne automatique. Windows les mises à jour doivent être transparentes dans la salle et le fonctionnement normal ne doit jamais être interrompu par Windows mises à jour.

Si vous choisissez d’utiliser des appareils de joint noms de domaine, vous pouvez utiliser Microsoft Endpoint Configuration Manager WSUS. Prêter une attention particulière aux stratégies ou actions qui entraînent une mise à jour de l’appareil ou un redémarrage forcé pendant les heures d’ouverture. salles Teams ne doivent pas redémarrer pendant l’utilisation, ni faire l’Windows mises à jour de l’interface utilisateur pendant les heures d’utilisation. Examinez votre configuration si ce comportement se produit.
