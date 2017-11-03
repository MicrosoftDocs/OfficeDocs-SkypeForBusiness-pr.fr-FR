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
<a name="office-365-dependencies-for-microsoft-teams"></a><span data-ttu-id="10d75-103">Dépendances Office 365 pour Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="10d75-103">Office 365 licensing for Microsoft Teams</span></span>
===========================================

<span data-ttu-id="10d75-104">Microsoft Teams s'appuie sur les groupes Office 365 pour stocker les appartenances aux équipes et les autres propriétés telles que les paramètres de classification des données des équipes.</span><span class="sxs-lookup"><span data-stu-id="10d75-104">In addition, Microsoft Teams relies on Office 365 groups to store teams' memberships and other properties such as team data classification settings.</span></span> <span data-ttu-id="10d75-105">Les groupes Office 365 sont un service disponible sous la forme d'un abonnement inter-applications qui donne accès à un ensemble de ressources partagées, telles qu'un site SharePoint ou un tableau de bord Power BI, pour permettre à l'équipe de collaborer efficacement et en toute sécurité.</span><span class="sxs-lookup"><span data-stu-id="10d75-105">Office 365 Groups is a service that provides cross-application membership for a set of shared team assets, like a SharePoint site or a Power BI dashboard, so that the team can collaborate effectively and securely.</span></span> 

<span data-ttu-id="10d75-106">Teams repose aussi sur SharePoint Online et OneDrive Entreprise pour stocker les fichiers et les documents des canaux et des conversations.</span><span class="sxs-lookup"><span data-stu-id="10d75-106">Teams relies on SharePoint Online and OneDrive for Business to store files and documents for channels and chat conversations.</span></span> <span data-ttu-id="10d75-107">De plus, Teams s'appuie sur les groupes Office 365 pour stocker les appartenances aux équipes et les autres propriétés telles que les paramètres de classification des données des équipes.</span><span class="sxs-lookup"><span data-stu-id="10d75-107">In addition, Teams relies on Office 365 groups to store teams' memberships and other properties such as team data classification settings.</span></span> <span data-ttu-id="10d75-108">Les invités sont soumis aux mêmes limites des services [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) et [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019).</span><span class="sxs-lookup"><span data-stu-id="10d75-108">Yes, guests are subject to  [Office 365](https://go.microsoft.com/fwlink/p/?linkid=282347) and [Azure Active Directory](https://go.microsoft.com/fwlink/p/?linkid=853019) service limits.</span></span>
  
    
    
<span data-ttu-id="10d75-109">Pour activer l'expérience complète de l'accès invité Teams, les administrateurs d'Office 365 doivent sélectionner **Activé** pour les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="10d75-109">To enable the full Teams guest access experience, Office 365 admins need to select **On** for the following settings:</span></span>
  
    
    

- <span data-ttu-id="10d75-110">Dans SharePoint Online : **Autoriser uniquement le partage avec les utilisateurs externes déjà dans le répertoire**</span><span class="sxs-lookup"><span data-stu-id="10d75-110">In SharePoint Online: **Only allow sharing with external users already in the directory**</span></span>
    
    <span data-ttu-id="10d75-111">Pour plus d'informations, reportez-vous à la rubrique [Gérer le partage externe de votre environnement SharePoint Online](https://support.office.com/en-us/article/Manage-external-sharing-for-your-SharePoint-Online-environment-c8a462eb-0723-4b0b-8d0a-70feafe4be85).</span><span class="sxs-lookup"><span data-stu-id="10d75-111">For more information, see [Manage external sharing for your SharePoint Online environment](https://support.office.com/en-us/article/Manage-external-sharing-for-your-SharePoint-Online-environment-c8a462eb-0723-4b0b-8d0a-70feafe4be85).</span></span>
    
  
- <span data-ttu-id="10d75-112">Dans les groupes Office 365 : **Autoriser les propriétaires de groupes à ajouter des personnes en dehors de l'organisation aux groupes**</span><span class="sxs-lookup"><span data-stu-id="10d75-112">In Office 365 groups: **Let group owners add people outside the organization to groups**</span></span>
    
    <span data-ttu-id="10d75-113">Pour plus d'informations, reportez-vous à la rubrique [Contrôler l'accès invité à Microsoft Teams](#controlguest).</span><span class="sxs-lookup"><span data-stu-id="10d75-113">For more information, see [Control guest access to Microsoft Teams](#controlguest).</span></span>
  

<span data-ttu-id="10d75-114">Vous pouvez gérer les paramètres d'utilisateur externe de SharePoint Online pour le site des équipes connectées à Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="10d75-114">Yes, you can manage SharePoint Online external user settings for the Teams connected team site.</span></span> <span data-ttu-id="10d75-115">Pour plus d'informations, reportez-vous à la rubrique [Gérer les paramètres de votre site des équipes SharePoint](https://support.office.com/en-us/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).</span><span class="sxs-lookup"><span data-stu-id="10d75-115">For more details, see  [Manage your SharePoint team site settings](https://support.office.com/en-us/article/Manage-your-SharePoint-team-site-settings-8376034d-d0c7-446e-9178-6ab51c58df42).</span></span>