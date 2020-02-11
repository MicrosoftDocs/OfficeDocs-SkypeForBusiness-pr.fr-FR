---
title: Stratégies de contrôle d’application AppLocker dans Microsoft teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: rafarhi
search.appverid: MET150
f1.keywords:
- NOCSH
description: Apprenez à activer l’application cliente de bureau teams avec des stratégies de contrôle d’application AppLocker.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 13a1afd4ad4089db3c6b0c1223bf06831d9be667
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888553"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a>Stratégies de contrôle d’application AppLocker dans Microsoft teams

Cet article explique comment activer l’application Microsoft teams cliente de bureau avec des stratégies de contrôle d’application AppLocker. L’utilisation de AppLocker a pour but de limiter l’exécution du programme et du script par des utilisateurs non administrateurs. Pour plus d’informations et des instructions sur AppLocker, voir [qu’est-ce que AppLocker ?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).

Le processus d’activation d’une équipe avec AppLocker nécessite la création de stratégies de création de listes de personnes basées sur AppLocker. Les stratégies sont créées à l’aide d’un logiciel de gestion des stratégies de groupe et/ou de l’utilisation des cmdlets Windows PowerShell pour AppLocker (voir [référence technique AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) pour plus d’informations). La stratégie AppLocker est enregistrée au format XML et peut être modifiée à l’aide d’un éditeur de texte ou XML.

## <a name="teams-whitelisting-with-applocker"></a>Teams, création de listes d’AppLocker

Les règles AppLocker sont organisées en collections de règles. Les règles AppLocker s’appliquent à l’application ciblée et sont les composants qui constituent la stratégie AppLocker.  

Pour les équipes de liste blanche, nous vous conseillons d’utiliser les [règles de condition Publisher](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) puisque tous les fichiers d’application teams sont signés numériquement.
  
Nous déconseillons l’utilisation de règles de chemin d’accès, car le répertoire d’installation de teams est accessible par l’utilisateur. Par ailleurs, nous ne recommandons pas l’utilisation des règles de hachage, car elles doivent être mises à jour à chaque mise à jour de l’application cliente Teams.

Dans la mesure où les fichiers exécutable de bureau teams sont signés numériquement, la condition d’éditeur identifie un fichier d’application en fonction de sa signature numérique et des attributs de version incorporés. La signature numérique contient des informations sur la société qui a créé le fichier d’application (l’éditeur). Les informations de version, obtenues à partir de la ressource binaire, incluent le nom du produit dont fait partie le fichier et le numéro de version du fichier d’application.

### <a name="example-of-publisher-condition-rules"></a>Exemple de règles de condition Publisher

Pour l’application client Teams (tous les fichiers, toutes les versions), ajoutez les éléments suivants aux règles d’exécution & règles de DLL :

```console
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
Product name: MICROSOFT TEAMS UPDATE
```

## <a name="related-topics"></a>Rubriques connexes
[Présentation d’AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker) 
 [Référence technique AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)
