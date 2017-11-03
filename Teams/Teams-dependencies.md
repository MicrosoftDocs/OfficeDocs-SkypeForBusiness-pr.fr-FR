---
title: "Dépendances Office 365 pour Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 10/20/17
ms.topic: article
ms.service: msteams
description: "Microsoft Teams repose sur des groupes Office 365, SharePoint Online et OneDrive Entreprise."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: e04770535976f509a8ac16cf054ea5e6760b5231
ms.sourcegitcommit: f6c2673a2ccd951770296972234938e627bd49ad
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2017
---
<a name="office-365-dependencies-for-microsoft-teams"></a>Dépendances Office 365 pour Microsoft Teams
===========================================

Microsoft Teams s'appuie sur les groupes Office 365 pour stocker les appartenances aux équipes et les autres propriétés telles que les paramètres de classification des données des équipes. Les groupes Office 365 sont un service disponible sous la forme d'un abonnement inter-applications qui donne accès à un ensemble de ressources partagées, telles qu'un site SharePoint ou un tableau de bord Power BI, pour permettre à l'équipe de collaborer efficacement et en toute sécurité. 

Teams repose aussi sur SharePoint Online et OneDrive Entreprise pour stocker les fichiers et les documents des canaux et des conversations. De plus, Teams s'appuie sur les groupes Office 365 pour stocker les appartenances aux équipes et les autres propriétés telles que les paramètres de classification des données des équipes. Les invités sont soumis aux mêmes limites des services [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) et [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019).
  
    
    
Pour activer l'expérience complète de l'accès invité Teams, les administrateurs d'Office 365 doivent sélectionner **Activé** pour les paramètres suivants :
  
    
    

- Dans SharePoint Online : **Autoriser uniquement le partage avec les utilisateurs externes déjà dans le répertoire**
    
    Pour plus d'informations, reportez-vous à la rubrique [Gérer le partage externe de votre environnement SharePoint Online](https://support.office.com/en-us/article/Manage-external-sharing-for-your-SharePoint-Online-environment-c8a462eb-0723-4b0b-8d0a-70feafe4be85).
    
  
- Dans les groupes Office 365 : **Autoriser les propriétaires de groupes à ajouter des personnes en dehors de l'organisation aux groupes**
    
    Pour plus d'informations, reportez-vous à la rubrique [Contrôler l'accès invité à Microsoft Teams](#controlguest).
  

Vous pouvez gérer les paramètres d'utilisateur externe de SharePoint Online pour le site des équipes connectées à Microsoft Teams. Pour plus d'informations, reportez-vous à la rubrique [Gérer les paramètres de votre site des équipes SharePoint](https://support.office.com/en-us/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).