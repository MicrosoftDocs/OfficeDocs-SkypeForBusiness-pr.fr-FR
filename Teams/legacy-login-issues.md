---
title: Problèmes de réception de messages et d’appels sur les anciens systèmes dans teams
ms.reviewer: ''
author: cichur
ms.author: v-cichur
manager: serdars
ms.date: 05/29/2020
ms.topic: troubleshooting
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
description: Résoudre les problèmes liés à la réception de messages et d’appels sur les systèmes hérités
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: af7845b5fd6d50d63be6cd21749cbfedc7669fcf
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085150"
---
<a name="issues-receiving-messages-and-calls-on-legacy-systems"></a><span data-ttu-id="18470-103">Problèmes de réception de messages et d’appels sur les systèmes hérités</span><span class="sxs-lookup"><span data-stu-id="18470-103">Issues receiving messages and calls on legacy systems</span></span>
==============================================================

<span data-ttu-id="18470-104">Les utilisateurs peuvent rencontrer des problèmes de réception de messages ou d’appels s’ils utilisent une version antérieure d’teams ou s’ils sont connectés avec d’autres applications.</span><span class="sxs-lookup"><span data-stu-id="18470-104">Users might have issues receiving messages or calls if they are using older versions of Teams or have logged in with other applications.</span></span>

## <a name="legacy-adu-setups"></a><span data-ttu-id="18470-105">ADUs léguées</span><span class="sxs-lookup"><span data-stu-id="18470-105">Legacy ADU setups</span></span>

 <span data-ttu-id="18470-106">Si les utilisateurs sont connectés à un ordinateur joint à un domaine et que vous **ne souhaitez pas que leur nom d’utilisateur soit déjà rempli sur l’écran de connexion à Teams**, les administrateurs peuvent définir le registre Windows suivant pour désactiver le pré-remplissage du nom d’utilisateur (UPN) :</span><span class="sxs-lookup"><span data-stu-id="18470-106">If users are signed in to a domain-joined computer and you **don't want their user name pre-populated on the Teams sign-in screen**, admins can set the following Windows registry to turn off pre-population of the user name (UPN):</span></span>

  <span data-ttu-id="18470-107">Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams</span><span class="sxs-lookup"><span data-stu-id="18470-107">Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams</span></span><br/>
  <span data-ttu-id="18470-108">SkipUpnPrefill(REG_DWORD)</span><span class="sxs-lookup"><span data-stu-id="18470-108">SkipUpnPrefill(REG_DWORD)</span></span><br/>
  <span data-ttu-id="18470-109">0x00000001 (1)</span><span class="sxs-lookup"><span data-stu-id="18470-109">0x00000001 (1)</span></span>

> [!NOTE]
> <span data-ttu-id="18470-110">Lorsque vous ignorez ou ignorez le nom d’utilisateur, les noms d’utilisateur qui se terminent par « . local » ou « . Corp » sont activés par défaut. vous n’avez donc pas besoin de définir une clé de Registre pour les désactiver.</span><span class="sxs-lookup"><span data-stu-id="18470-110">Skipping or ignoring user name pre-fill for user names that end in ".local" or ".corp" is on by default, so you don't need to set a registry key to turn these off.</span></span>

<span data-ttu-id="18470-111">Pour plus d’informations, reportez-vous [à se connecter à Microsoft teams avec l’authentification moderne](sign-in-teams.md) .</span><span class="sxs-lookup"><span data-stu-id="18470-111">See [Sign in to Microsoft Teams using modern authentication](sign-in-teams.md) for more information.</span></span>

## <a name="skype-token-revocation"></a><span data-ttu-id="18470-112">Révocation de jeton Skype</span><span class="sxs-lookup"><span data-stu-id="18470-112">Skype token revocation</span></span>

<span data-ttu-id="18470-113">Lors de la modification/réinitialisation d’un mot de passe, les clients plus anciens ne recevront pas de messages et d’appels pendant une heure.</span><span class="sxs-lookup"><span data-stu-id="18470-113">When changing/resetting a password, older clients will not receive messages and calls for up to an hour.</span></span> <span data-ttu-id="18470-114">Pour résoudre ce problème, redémarrez l’application ou accédez à un client plus récent.</span><span class="sxs-lookup"><span data-stu-id="18470-114">To resolve this issue, either restart the app or move to newer clients.</span></span>


## <a name="related-topics"></a><span data-ttu-id="18470-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="18470-115">Related topics</span></span>

[<span data-ttu-id="18470-116">Résolution des problèmes de Teams</span><span class="sxs-lookup"><span data-stu-id="18470-116">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)