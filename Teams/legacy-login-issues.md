---
title: Problèmes de réception de messages et d’appels sur des systèmes hérités dans Teams
ms.reviewer: ''
author: HowlinWolf-92
ms.author: v-mahoffman
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
ms.openlocfilehash: 69a3f070b247507e0d22535179353860434e94ad
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60857141"
---
# <a name="issues-receiving-messages-and-calls-on-legacy-systems"></a>Problèmes de réception de messages et d’appels sur des systèmes hérités

Les utilisateurs peuvent avoir des problèmes pour recevoir des messages ou des appels s’ils utilisent des versions antérieures d’Teams ou s’ils se sont connectés avec d’autres applications.

## <a name="legacy-adu-setups"></a>Configurations ADU héritées

 Si les utilisateurs sont connectés à un ordinateur joint à un domaine et que vous **ne souhaitez pas que leur nom d’utilisateur soit déjà rempli sur l’écran de connexion à Teams**, les administrateurs peuvent définir le registre Windows suivant pour désactiver le pré-remplissage du nom d’utilisateur (UPN) :

  Computer\HKEY_CURRENT_USER\Software\Microsoft\Office\Teams<br/>
  SkipUpnPrefill(REG_DWORD)<br/>
  0x00000001 (1)

> [!NOTE]
> Lorsque vous ignorez ou ignorez le nom d’utilisateur, les noms d’utilisateur qui se terminent par « . local » ou « . Corp » sont activés par défaut. vous n’avez donc pas besoin de définir une clé de Registre pour les désactiver.

Pour [plus d’informations, voir Se Microsoft Teams à l’aide](sign-in-teams.md) de l’authentification moderne.

## <a name="skype-token-revocation"></a>Skype révocation de jeton

Lors de la modification/réinitialisation d’un mot de passe, les clients plus anciens ne recevront pas de messages et d’appels pendant une heure. Pour résoudre ce problème, redémarrez l’application ou déplacez-vous vers des clients plus nouveaux.


## <a name="related-topics"></a>Voir aussi

[Résolution des problèmes de Teams](/MicrosoftTeams/troubleshoot/teams)