---
title: Problèmes de réception de messages et d’appels sur les systèmes hérités dans Teams
ms.reviewer: ''
author: CarolynRowe
ms.author: crowe
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
ms.openlocfilehash: 56499af9534c3559cdfa3311a360caa60d06d3d7
ms.sourcegitcommit: 0dda332951df3b946097d90a4923eb191fd86b4c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/14/2022
ms.locfileid: "66789519"
---
# <a name="issues-receiving-messages-and-calls-on-legacy-systems"></a>Problèmes de réception de messages et d’appels sur les systèmes hérités

Les utilisateurs peuvent rencontrer des problèmes de réception de messages ou d’appels s’ils utilisent des versions antérieures de Teams ou s’ils se sont connectés avec d’autres applications.

## <a name="legacy-adu-setups"></a>Configurations ADU héritées

 Si les utilisateurs sont connectés à un ordinateur joint à un domaine et que vous **ne souhaitez pas que leur nom d’utilisateur soit déjà rempli sur l’écran de connexion à Teams**, les administrateurs peuvent définir le registre Windows suivant pour désactiver le pré-remplissage du nom d’utilisateur (UPN) :

  Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams<br/>
  SkipUpnPrefill(REG_DWORD)<br/>
  0x00000001 (1)

> [!NOTE]
> Lorsque vous ignorez ou ignorez le nom d’utilisateur, les noms d’utilisateur qui se terminent par « . local » ou « . Corp » sont activés par défaut. vous n’avez donc pas besoin de définir une clé de Registre pour les désactiver.

Pour plus [d’informations, consultez Se connecter à Microsoft Teams à l’aide de l’authentification moderne](sign-in-teams.md) .

## <a name="skype-token-revocation"></a>Révocation de jeton Skype

Lors de la modification/réinitialisation d’un mot de passe, les clients plus anciens ne reçoivent pas de messages et d’appels pendant une heure maximum. Pour résoudre ce problème, redémarrez l’application ou déplacez-vous vers des clients plus récents.


## <a name="related-topics"></a>Voir aussi

[Résolution des problèmes de Teams](/MicrosoftTeams/troubleshoot/teams)