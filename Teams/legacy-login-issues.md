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
<a name="issues-receiving-messages-and-calls-on-legacy-systems"></a>Problèmes de réception de messages et d’appels sur les systèmes hérités
==============================================================

Les utilisateurs peuvent rencontrer des problèmes de réception de messages ou d’appels s’ils utilisent une version antérieure d’teams ou s’ils sont connectés avec d’autres applications.

## <a name="legacy-adu-setups"></a>ADUs léguées

 Si les utilisateurs sont connectés à un ordinateur joint à un domaine et que vous **ne souhaitez pas que leur nom d’utilisateur soit déjà rempli sur l’écran de connexion à Teams**, les administrateurs peuvent définir le registre Windows suivant pour désactiver le pré-remplissage du nom d’utilisateur (UPN) :

  Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams<br/>
  SkipUpnPrefill(REG_DWORD)<br/>
  0x00000001 (1)

> [!NOTE]
> Lorsque vous ignorez ou ignorez le nom d’utilisateur, les noms d’utilisateur qui se terminent par « . local » ou « . Corp » sont activés par défaut. vous n’avez donc pas besoin de définir une clé de Registre pour les désactiver.

Pour plus d’informations, reportez-vous [à se connecter à Microsoft teams avec l’authentification moderne](sign-in-teams.md) .

## <a name="skype-token-revocation"></a>Révocation de jeton Skype

Lors de la modification/réinitialisation d’un mot de passe, les clients plus anciens ne recevront pas de messages et d’appels pendant une heure. Pour résoudre ce problème, redémarrez l’application ou accédez à un client plus récent.


## <a name="related-topics"></a>Voir aussi

[Résolution des problèmes de Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)