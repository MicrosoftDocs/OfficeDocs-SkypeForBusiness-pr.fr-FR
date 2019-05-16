---
title: Stratégies de contrôle d’application AppLocker dans Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: rafarhi
search.appverid: MET150
description: Découvrez comment activer le client de bureau équipes avec les stratégies de contrôle d’application AppLocker.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 04379cad0ab224915a02475b010f908d486284cc
ms.sourcegitcommit: 85b135cf622c9e9eb1857ef953bc618dc2cdb51e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "34063208"
---
# <a name="applocker-application-control-policies-in-microsoft-teams"></a>Stratégies de contrôle d’application AppLocker dans Microsoft Teams

Cet article explique comment activer l’application de client de bureau équipes avec les stratégies de contrôle d’application AppLocker. Utilisation de AppLocker est conçue pour restreindre l’exécution du programme et script par les utilisateurs non administratifs. Pour plus d’informations et pour obtenir des instructions sur AppLocker, consultez la rubrique [What ' s AppLocker ?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker).

Le processus d’activation des équipes avec AppLocker requiert la création de stratégies de création de listes autorisées basée sur AppLocker. Les stratégies sont créées avec l’utilisation des applets de commande Windows PowerShell pour AppLocker et/ou le logiciel de gestion de stratégie de groupe (voir la [référence technique AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference) pour plus d’informations). La stratégie AppLocker est enregistrée au format XML et peut être modifiée avec n’importe quel texte ou un éditeur XML.

## <a name="teams-whitelisting-with-applocker"></a>Création de listes autorisées équipes avec AppLocker

Règles AppLocker sont organisés en ensembles de règles. Appliquent des règles AppLocker à l’application cible, et elles sont les composants qui constituent la stratégie AppLocker.  

Aux équipes d’autorisation, nous vous recommandons d’utiliser les [règles de condition publisher](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/understanding-the-publisher-rule-condition-in-applocker) étant donné que tous les fichiers d’application équipes sont signés numériquement.
  
L’utilisation de règles de chemin d’accès est déconseillée, car le répertoire d’installation équipes est accessible en écriture pour un utilisateur. Également n’est pas recommandé l’utilisation de règles de hachage, car les règles devra être mis à jour chaque fois que l’application cliente les équipes est mis à jour.

Dans la mesure où les fichiers exécutables du bureau équipes sont signés numériquement, la condition éditeur identifie un fichier d’application en fonction de sa signature numérique et les attributs de version incorporées. La signature numérique contient des informations sur la société qui a créé le fichier d’application (l’éditeur). Les informations de version, qui sont obtenues à partir de la ressource binaire, incluent le nom du produit faisant partie de fichier et le numéro de version du fichier d’application.

### <a name="example-of-publisher-condition-rules"></a>Exemple de règles de condition publisher

Pour l’application cliente équipes (tous les fichiers, toutes les versions) :

```
Publisher: O=MICROSOFT CORPORATION, L=REDMOND, S=WASHINGTON, C=US
Product name: MICROSOFT TEAMS
```

## <a name="related-topics"></a>Voir aussi
[What ' s AppLocker ?](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/what-is-applocker) 
 [AppLocker Guide de référence technique](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-technical-reference)