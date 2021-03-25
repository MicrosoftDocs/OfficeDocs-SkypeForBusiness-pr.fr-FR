---
title: Problèmes de réception de messages et d’appels sur des systèmes hérités dans Teams
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
description: Résoudre les problèmes liés à la réception de messages et d’appels sur des systèmes hérités
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1c209d1acc83e63792722b00b63be5a6b9f3721a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120605"
---
<a name="issues-receiving-messages-and-calls-on-legacy-systems"></a><span data-ttu-id="1b463-103">Problèmes de réception de messages et d’appels sur des systèmes hérités</span><span class="sxs-lookup"><span data-stu-id="1b463-103">Issues receiving messages and calls on legacy systems</span></span>
==============================================================

<span data-ttu-id="1b463-104">Les utilisateurs peuvent avoir des problèmes pour recevoir des messages ou des appels s’ils utilisent des versions antérieures de Teams ou s’ils se sont connectés avec d’autres applications.</span><span class="sxs-lookup"><span data-stu-id="1b463-104">Users might have issues receiving messages or calls if they are using older versions of Teams or have logged in with other applications.</span></span>

## <a name="legacy-adu-setups"></a><span data-ttu-id="1b463-105">Configurations ADU héritées</span><span class="sxs-lookup"><span data-stu-id="1b463-105">Legacy ADU setups</span></span>

 <span data-ttu-id="1b463-106">Si les utilisateurs sont connectés à un ordinateur joint à un domaine et que vous **ne souhaitez pas que leur nom d’utilisateur soit déjà rempli sur l’écran de connexion à Teams**, les administrateurs peuvent définir le registre Windows suivant pour désactiver le pré-remplissage du nom d’utilisateur (UPN) :</span><span class="sxs-lookup"><span data-stu-id="1b463-106">If users are signed in to a domain-joined computer and you **don't want their user name pre-populated on the Teams sign-in screen**, admins can set the following Windows registry to turn off pre-population of the user name (UPN):</span></span>

  <span data-ttu-id="1b463-107">Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams</span><span class="sxs-lookup"><span data-stu-id="1b463-107">Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams</span></span><br/>
  <span data-ttu-id="1b463-108">SkipUpnPrefill(REG_DWORD)</span><span class="sxs-lookup"><span data-stu-id="1b463-108">SkipUpnPrefill(REG_DWORD)</span></span><br/>
  <span data-ttu-id="1b463-109">0x00000001 (1)</span><span class="sxs-lookup"><span data-stu-id="1b463-109">0x00000001 (1)</span></span>

> [!NOTE]
> <span data-ttu-id="1b463-110">Lorsque vous ignorez ou ignorez le nom d’utilisateur, les noms d’utilisateur qui se terminent par « . local » ou « . Corp » sont activés par défaut. vous n’avez donc pas besoin de définir une clé de Registre pour les désactiver.</span><span class="sxs-lookup"><span data-stu-id="1b463-110">Skipping or ignoring user name pre-fill for user names that end in ".local" or ".corp" is on by default, so you don't need to set a registry key to turn these off.</span></span>

<span data-ttu-id="1b463-111">Pour plus [d’informations, voir](sign-in-teams.md) Se connectez-vous à Microsoft Teams à l’aide de l’authentification moderne.</span><span class="sxs-lookup"><span data-stu-id="1b463-111">See [Sign in to Microsoft Teams using modern authentication](sign-in-teams.md) for more information.</span></span>

## <a name="skype-token-revocation"></a><span data-ttu-id="1b463-112">Révocation de jeton Skype</span><span class="sxs-lookup"><span data-stu-id="1b463-112">Skype token revocation</span></span>

<span data-ttu-id="1b463-113">Lors de la modification ou de la réinitialisation d’un mot de passe, les clients plus anciens ne recevront pas de messages et d’appels pendant une heure.</span><span class="sxs-lookup"><span data-stu-id="1b463-113">When changing/resetting a password, older clients will not receive messages and calls for up to an hour.</span></span> <span data-ttu-id="1b463-114">Pour résoudre ce problème, redémarrez l’application ou déplacez-vous vers des clients plus nouveaux.</span><span class="sxs-lookup"><span data-stu-id="1b463-114">To resolve this issue, either restart the app or move to newer clients.</span></span>


## <a name="related-topics"></a><span data-ttu-id="1b463-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1b463-115">Related topics</span></span>

[<span data-ttu-id="1b463-116">Résolution des problèmes de Teams</span><span class="sxs-lookup"><span data-stu-id="1b463-116">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)