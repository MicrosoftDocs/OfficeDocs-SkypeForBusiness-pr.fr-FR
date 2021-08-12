---
title: Stratégies de contrôle AppLocker
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: rafarhi
search.appverid: MET150
f1.keywords:
- NOCSH
description: Découvrez comment activer l’application Teams client de bureau avec des stratégies de contrôle d’application AppLocker.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: b68d698ffcb703e70e12f3801ff70fb0719bb17cb09e23facf47121529a86b0b
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54288442"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a>Stratégies de contrôle d’application AppLocker dans Microsoft Teams

Cet article explique comment activer l’application cliente Teams bureau à l’application AppLocker. L’utilisation d’AppLocker est conçue pour restreindre l’exécution des programmes et scripts par les utilisateurs non administratifs. Pour plus d’informations et des conseils sur AppLocker, voir [Qu’est-ce qu’AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker)?

Le processus d’activation Teams appLocker nécessite la création de stratégies d’activation de listes autorises basées sur AppLocker. Les stratégies sont créées avec un logiciel de gestion des stratégies de groupe et/ou l’utilisation d’Windows PowerShell cmdlets pour AppLocker (voir la référence technique [AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) pour plus d’informations). La stratégie AppLocker est enregistrée au format XML et peut être modifiée avec n’importe quel éditeur de texte ou XML.

## <a name="teams-allow-list-with-applocker"></a>Teams liste d’applications avec AppLocker

Les règles AppLocker sont organisées en collections de règles. Les règles AppLocker s’appliquent à l’application ciblée et elles sont les composants qui font partie de la stratégie AppLocker.  

Pour autoriser les Teams, nous vous recommandons d’utiliser les règles de [condition](/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) de l’éditeur, car tous Teams fichiers d’application sont signés numériquement.
  
Nous vous déconseillons d’utiliser des règles de chemin d’accès, car le Teams d’installation peut être accessible par les utilisateurs. Par ailleurs, nous vous déconseillons d’utiliser des règles de hachage, car elles doivent être mises à jour chaque fois que l’Teams client est mise à jour.

Dans Teams fichiers exécutables du bureau sont signés numériquement, la condition de l’éditeur identifie un fichier d’application en fonction de sa signature numérique et des attributs de version incorporés. La signature numérique contient des informations sur la société qui a créé le fichier d’application (l’éditeur). Les informations de version, obtenues à partir de la ressource binaire, incluent le nom du produit dont fait partie le fichier et le numéro de version du fichier d’application.

### <a name="example-of-publisher-condition-rules"></a>Exemples de règles de condition de l’éditeur

Pour l’Teams client (tous les fichiers, toutes les versions) ajoutez ce qui suit aux règles exécutables & DLL :

```console
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
Product name: MICROSOFT TEAMS UPDATE
```

## <a name="related-topics"></a>Voir aussi
[Qu’est-ce que AppLocker ?](/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker) 
 [Référence technique AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)