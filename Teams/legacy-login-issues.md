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
ms.openlocfilehash: 52038470e81b825391e4176c07af7a30f51356df
ms.sourcegitcommit: ef3cd762e799df43bdcde03363c501d7ca9bb6b3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/01/2020
ms.locfileid: "44489159"
---
<a name="issues-receiving-messages-and-calls-on-legacy-systems"></a><span data-ttu-id="88f9b-103">Problèmes de réception de messages et d’appels sur les systèmes hérités</span><span class="sxs-lookup"><span data-stu-id="88f9b-103">Issues receiving messages and calls on legacy systems</span></span>
==============================================================

<span data-ttu-id="88f9b-104">Les utilisateurs peuvent rencontrer des problèmes de réception de messages ou d’appels s’ils utilisent une version antérieure d’teams ou s’ils sont connectés avec d’autres applications.</span><span class="sxs-lookup"><span data-stu-id="88f9b-104">Users might have issues receiving messages or calls if they are using older versions of Teams or have logged in with other applications.</span></span>

## <a name="legacy-adu-setups"></a><span data-ttu-id="88f9b-105">ADUs léguées</span><span class="sxs-lookup"><span data-stu-id="88f9b-105">Legacy ADU setups</span></span>

 <span data-ttu-id="88f9b-106">Si les utilisateurs sont connectés à un ordinateur joint à un domaine et que vous **ne souhaitez pas que leur nom d’utilisateur soit déjà rempli sur l’écran de connexion à Teams**, les administrateurs peuvent définir le registre Windows suivant pour désactiver le pré-remplissage du nom d’utilisateur (UPN) :</span><span class="sxs-lookup"><span data-stu-id="88f9b-106">If users are signed in to a domain-joined computer and you **don't want their user name pre-populated on the Teams sign-in screen**, admins can set the following Windows registry to turn off pre-population of the user name (UPN):</span></span>

  <span data-ttu-id="88f9b-107">Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams</span><span class="sxs-lookup"><span data-stu-id="88f9b-107">Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams</span></span><br/>
  <span data-ttu-id="88f9b-108">SkipUpnPrefill(REG_DWORD)</span><span class="sxs-lookup"><span data-stu-id="88f9b-108">SkipUpnPrefill(REG_DWORD)</span></span><br/>
  <span data-ttu-id="88f9b-109">0x00000001 (1)</span><span class="sxs-lookup"><span data-stu-id="88f9b-109">0x00000001 (1)</span></span>

> [!NOTE]
> <span data-ttu-id="88f9b-110">Lorsque vous ignorez ou ignorez le nom d’utilisateur, les noms d’utilisateur qui se terminent par « . local » ou « . Corp » sont activés par défaut. vous n’avez donc pas besoin de définir une clé de Registre pour les désactiver.</span><span class="sxs-lookup"><span data-stu-id="88f9b-110">Skipping or ignoring user name pre-fill for user names that end in ".local" or ".corp" is on by default, so you don't need to set a registry key to turn these off.</span></span>

<span data-ttu-id="88f9b-111">Pour plus d’informations, reportez-vous [à se connecter à Microsoft teams avec l’authentification moderne](sign-in-teams.md) .</span><span class="sxs-lookup"><span data-stu-id="88f9b-111">See [Sign in to Microsoft Teams using modern authentication](sign-in-teams.md) for more information.</span></span>

## <a name="skype-token-revocation"></a><span data-ttu-id="88f9b-112">Révocation de jeton Skype</span><span class="sxs-lookup"><span data-stu-id="88f9b-112">Skype token revocation</span></span>

<span data-ttu-id="88f9b-113">Lors de la modification/réinitialisation d’un mot de passe, les clients plus anciens ne recevront pas de messages et d’appels pendant une heure.</span><span class="sxs-lookup"><span data-stu-id="88f9b-113">When changing/resetting a password, older clients will not receive messages and calls for up to an hour.</span></span> <span data-ttu-id="88f9b-114">Pour résoudre ce problème, redémarrez l’application ou accédez à un client plus récent.</span><span class="sxs-lookup"><span data-stu-id="88f9b-114">To resolve this issue, either restart the app or move to newer clients.</span></span>
