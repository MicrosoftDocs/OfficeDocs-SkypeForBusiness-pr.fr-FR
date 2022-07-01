---
title: Implémenter la qualité de service (QoS) dans les clients Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: Découvrez comment utiliser la qualité de service (QoS) pour optimiser le trafic réseau pour le client de bureau Microsoft Teams.
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: 70dbc5794fe64a1afed86bc82d0005ad7d510c5f
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/30/2022
ms.locfileid: "66563922"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams-clients"></a>Implémenter la qualité de service (QoS) dans les clients Microsoft Teams

Vous pouvez utiliser QoS (Quality of Service) basé sur des stratégies dans stratégie de groupe pour définir la plage de ports source pour la valeur DSCP prédéfinie dans le client Teams. Les plages de ports spécifiées dans le tableau suivant constituent un point de départ pour créer une stratégie pour chaque charge de travail.

*Tableau 1. Plages de ports initiales recommandées*

|Type de trafic média| Plage de port source du client  |Protocole|Valeur DSCP|Classe DSCP|
|:--- |:--- |:--- |:--- |:--- |
|Audio| Entre 50 000 et 50 019|TCP/UDP|46|Acheminement accéléré (EF)|
|Vidéo| 50 020–50 039|TCP/UDP|34|Acheminement assuré (AF41)|
|Partage d’application/d'écran| 50 040–50 059|TCP/UDP|18|Transfert garanti (AF21)|
| | | | | |

Dans la mesure du possible, configurez les paramètres QoS basés sur des stratégies dans un objet stratégie de groupe. Les étapes suivantes sont très similaires à la [configuration des plages de ports et à une stratégie de qualité de service pour vos clients sur Skype Entreprise Server](/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), qui contient des détails supplémentaires qui peuvent ne pas être nécessaires.

Pour créer une stratégie audio QoS pour les ordinateurs Windows 10 joints à un domaine, commencez par vous connecter à un ordinateur sur lequel stratégie de groupe Management a été installé. Ouvrez stratégie de groupe Gestion (cliquez sur Démarrer, pointez sur Outils d’administration, puis cliquez sur stratégie de groupe Gestion), puis effectuez les étapes suivantes :

1. Dans stratégie de groupe Gestion, recherchez le conteneur où la nouvelle stratégie doit être créée. Par exemple, si tous vos ordinateurs clients se trouvent dans une unité d’organisation nommée **Clients**, la nouvelle stratégie doit être créée dans l’unité d’organisation clients.

1. Cliquez avec le bouton droit sur le conteneur approprié, puis cliquez sur **Créer un objet de stratégie de groupe dans ce domaine, puis liez-le ici**.

1. Dans la boîte de dialogue **Nouvel objet de stratégie** de groupe, tapez un nom pour le nouvel objet stratégie de groupe dans la zone **Nom**, puis cliquez sur **OK**.

1. Cliquez avec le bouton droit sur la stratégie nouvellement créée, puis cliquez sur **Modifier**.

1. Dans l’éditeur de gestion stratégie de groupe, développez **Configuration de l’ordinateur**, **développez Paramètres Windows**, cliquez avec le bouton droit sur **QoS basé sur la stratégie**, puis cliquez sur **Créer une stratégie**.

1. Dans la boîte **de dialogue QoS basée sur** la stratégie, dans la page d’ouverture, tapez un nom pour la nouvelle stratégie dans la zone **Nom** . Sélectionnez **Spécifier la valeur DSCP** et définissez la valeur sur **46**. Laissez **spécifiez le taux de limitation sortant** non sélectionné, puis cliquez sur **Suivant**.

1. Dans la page suivante, sélectionnez **Uniquement les applications avec ce nom exécutable** , entrez le nom **Teams.exe**, puis cliquez sur **Suivant**. Ce paramètre indique à la stratégie de hiérarchiser uniquement le trafic correspondant à partir du client Teams.

1. Sur la troisième page, assurez-vous que toutes les **adresses IP sources** et **toutes les adresses IP de destination** sont sélectionnées, puis cliquez sur **Suivant**. Ces deux paramètres garantissent que les paquets sont gérés indépendamment de l’ordinateur (adresse IP) qui a envoyé les paquets et de l’ordinateur (adresse IP) qui recevra les paquets.

1. À la page 4, sélectionnez **TCP et UDP** dans la liste déroulante **Sélectionner le protocole que cette stratégie QoS applique** . TCP (Transmission Control Protocol) et UDP (User Datagram Protocol) sont les deux protocoles réseau les plus couramment utilisés.

1. Sous **l’en-tête Spécifier le numéro de port source**, sélectionnez **À partir de ce port ou plage source**. Dans la zone de texte qui l’accompagne, tapez la plage de ports réservée aux transmissions audio. Par exemple, si vous avez réservé les ports 50000 à ports 50019 pour le trafic audio, entrez la plage de ports au format **suivant : 50000:50019**. Cliquez sur **Terminer**.

1. Répétez les étapes 5 à 10 pour créer des stratégies pour le partage vidéo et d’application/bureau, en remplaçant les valeurs appropriées aux étapes 6 et 10.

Les nouvelles stratégies que vous avez créées n’entreront pas en vigueur tant que stratégie de groupe n’aura pas été actualisée sur vos ordinateurs clients. Bien que stratégie de groupe régulièrement actualise de manière autonome, vous pouvez forcer une actualisation immédiate en procédant comme suit :

1. Sur chaque ordinateur pour lequel vous souhaitez actualiser stratégie de groupe, ouvrez une invite de commandes en tant qu’administrateur (*Exécuter en tant qu’administrateur*).

1. À l’invite de commandes, entrez

   ```console
   gpupdate /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a>Vérifier les marquages DSCP dans l’objet stratégie de groupe

Pour vérifier que les valeurs de l’objet stratégie de groupe ont été définies, procédez comme suit :

1. Ouvrez une invite de commandes en tant qu’administrateur (*Exécuter en tant qu’administrateur*).

1. À l’invite de commandes, entrez

   ```console
   gpresult /R > gp.txt
   ```

   Cela génère un rapport d’objets de stratégie de groupe appliqués et l’envoie à un fichier texte nommé *gp.txt*.

   Pour obtenir un rapport HTML plus lisible nommé *gp.html*, entrez la commande suivante :

   ```console
   gpresult /H gp.html
   ```

1. Dans le fichier généré, recherchez l’en-tête **Applied stratégie de groupe Objects** et vérifiez que les noms des objets stratégie de groupe créés précédemment figurent dans la liste des stratégies appliquées.

1. Ouvrez l’Éditeur du Registre, puis accédez à

   Stratégies logicielles HKEY\_LOCAL\_MACHINE\\Microsoft\\Windows\\QoS\\\\

   Vérifiez les valeurs des entrées de Registre répertoriées dans le tableau 2.

   *Tableau 2. Valeurs des entrées de Registre Windows pour QoS*

   |          Nom          |  Type  |    Données     |
   |         :---:          | :---:  |    :---:    |
   |    Nom de l’application    | REG_SZ |  Teams.exe  |
   |       Valeur DSCP       | REG_SZ |     46      |
   |        Adresse IP locale        | REG_SZ |     \*      |
   | Longueur du préfixe IP local | REG_SZ |     \*      |
   |       Local Port       | REG_SZ | 50000-50019 |
   |        Protocol (Protocole)        | REG_SZ |     \*      |
   |       Adresse IP distante        | REG_SZ |     \*      |
   |    Préfixe IP distant    | REG_SZ |     \*      |
   |      Port distant       | REG_SZ |     \*      |
   |     Vitesse de limitation      | REG_SZ |     -1      |
   | | | |

1. Vérifiez que la valeur de l’entrée Nom de l’application est correcte pour le client que vous utilisez, et vérifiez que les entrées de valeur DSCP et de port local reflètent les paramètres de l’objet stratégie de groupe.


## <a name="related-topics"></a>Sujets associés

[Implémenter la qualité de service (QoS) dans Teams](QoS-in-Teams.md)