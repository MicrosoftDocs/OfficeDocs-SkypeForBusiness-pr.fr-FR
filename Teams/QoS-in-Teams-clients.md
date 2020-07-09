---
title: Mise en œuvre de la qualité de service (QoS) pour les clients Microsoft teams
author: lolajacobsen
ms.author: lolaj
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: Découvrez comment utiliser la qualité de service (QoS) pour optimiser le trafic réseau pour le client de bureau Microsoft Teams.
ms.custom: seo-marvel-mar2020
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 80b9257abbbb873b30367f9d430e9a8d155cda09
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085530"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams-clients"></a>Mise en œuvre de la qualité de service (QoS) pour les clients Microsoft teams

Vous pouvez utiliser la qualité de service (QoS) basée sur les stratégies dans une stratégie de groupe pour définir la plage de ports sources pour la valeur DSCP prédéfinie dans le client Teams. Les plages de port spécifiées dans le tableau suivant constituent un point de départ pour créer une stratégie pour chaque charge de travail.

*Tableau 1. Plages de port initiales recommandées*

|Type de trafic média| Plage de port source du client  |Protocole|Valeur DSCP|Classe DSCP|
|:--- |:--- |:--- |:--- |:--- |
|Audio| Entre 50 000 et 50 019|TCP/UDP|46|Acheminement accéléré (EF)|
|Vidéo| 50 020–50 039|TCP/UDP|34|Acheminement assuré (AF41)|
|Partage d’application/d'écran| 50 040–50 059|TCP/UDP|19|Transfert garanti (AF21)|
| | | | | |

Dans la mesure du possible, vous pouvez configurer les paramètres de QoS basée sur une stratégie au sein d’un objet de stratégie de groupe. Les étapes suivantes sont similaires à la [configuration de plages de ports et d’une politique de qualité de service pour vos clients sur Skype entreprise Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), qui comporte des informations supplémentaires qui peuvent ne pas être nécessaires.

Pour créer une stratégie audio QoS pour des ordinateurs Windows 10 liés à un domaine, vous devez d’abord vous connecter à un ordinateur sur lequel est installée la gestion des stratégies de groupe. Ouvrez gestion des stratégies de groupe (cliquez sur Démarrer, pointez sur outils d’administration, cliquez sur gestion des stratégies de groupe), puis procédez comme suit :

1. Dans gestion des stratégies de groupe, recherchez le conteneur dans lequel la nouvelle stratégie doit être créée. Par exemple, si tous vos ordinateurs clients se trouvent dans une unité d’organisation nommée **clients**, la nouvelle stratégie doit être créée dans l’unité d’organisation clients.

1. Cliquez avec le bouton droit sur le conteneur approprié, puis cliquez sur **créer un objet de stratégie de groupe dans ce domaine et liez-le ici**.

1. Dans la boîte de dialogue **nouvel objet GPO** , entrez un nom pour le nouvel objet de stratégie de groupe dans la zone **nom** , puis cliquez sur **OK**.

1. Cliquez avec le bouton droit sur la stratégie que vous venez de créer, puis cliquez sur **modifier**.

1. Dans l’éditeur de gestion des stratégies de groupe, développez **Configuration ordinateur**, développez **Paramètres Windows**, cliquez avec le bouton droit sur **QoS basée sur une stratégie**, puis cliquez sur **créer une nouvelle stratégie**.

1. Dans la boîte de dialogue **QoS basée sur une stratégie** , dans la page d’ouverture, tapez un nom pour la nouvelle stratégie dans la zone **nom** . Sélectionnez **spécifier la valeur DSCP** et définissez la valeur sur **46**. Laissez l’option **spécifier le taux de limitation en sortie** non sélectionnée, puis cliquez sur **suivant**.

1. Sur la page suivante, sélectionnez **uniquement les applications ayant ce nom d’exécutable** , entrez le nom **Teams.exe**, puis cliquez sur **suivant**. Ce paramètre indique à la stratégie de classer uniquement le trafic correspondant du client Teams.

1. Sur la troisième page, assurez-vous que toutes les **adresses IP source** et **adresse IP de destination** sont sélectionnées, puis cliquez sur **suivant**. Ces deux paramètres garantissent le fonctionnement de la gestion des paquets indépendamment de l’ordinateur (adresse IP) ayant envoyé les paquets et de l’ordinateur (adresse IP) recevant les paquets.

1. Dans la page 4, sélectionnez **TCP et UDP** dans la liste déroulante **Sélectionner le protocole que cette stratégie de QoS applique à** . TCP (Transmission Control Protocol) et UDP (User Datagram Protocol) sont les deux protocoles réseau les plus fréquemment utilisés.

1. Sous le titre **Spécifiez le numéro de port source**, sélectionnez **à partir de ce port ou plage de sources**. Dans la zone texte de l’accompagnement, tapez la plage de ports réservée aux transmissions audio. Par exemple, si vous avez réservé ports 50000 via ports 50019 pour le trafic audio, entrez la plage de ports à l’aide du format suivant : **50000:50019**. Cliquez sur **Terminer**.

1. Répétez les étapes 5-10 pour créer des stratégies pour la vidéo et le partage de bureau et d’application

Les nouvelles stratégies que vous avez créées ne prennent effet qu’après la réactualisation de la stratégie de groupe sur les ordinateurs clients. Bien que la stratégie de groupe s’actualise périodiquement, vous pouvez forcer une actualisation immédiate en procédant comme suit :

1. Sur chaque ordinateur pour lequel vous voulez actualiser une stratégie de groupe, ouvrez une invite de commandes en tant qu’administrateur (*exécuter en tant qu’administrateur*).

1. À l’invite de commandes, entrez

   ```console
   gpupdate /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a>Vérifier les marquages DSCP dans l’objet de stratégie de groupe

Pour vérifier que les valeurs de l’objet de stratégie de groupe ont été définies, procédez comme suit :

1. Ouvrez une invite de commandes en tant qu’administrateur (*exécuter en tant qu’administrateur*).

1. À l’invite de commandes, entrez

   ```console
   gpresult /R > gp.txt
   ```

   Cette opération génère un rapport des objets de stratégie de groupe appliqués et les envoie à un fichier texte nommé *gp.txt*.

   Pour un rapport HTML plus lisible intitulé *gp.html*, entrez la commande suivante :

   ```console
   gpresult /H gp.html
   ```

1. Dans le fichier généré, recherchez le titre **appliqué objets de stratégie de groupe** , puis vérifiez que les noms des objets de stratégie de groupe créés précédemment figurent dans la liste des stratégies appliquées.

1. Ouvrez l’éditeur du Registre et accédez à

   HKEY \_ stratégies de logiciels de l' \_ ordinateur local \\ \\ \\ Microsoft \\ Windows \\ QoS

   Vérifiez les valeurs des entrées de registre indiquées dans le tableau 2.

   *Tableau 2. Valeurs pour les entrées de Registre Windows pour QoS*

   |          Nom          |  Type  |    Données     |
   |         :---:          | :---:  |    :---:    |
   |    Nom de l’application    | REG_SZ |  Teams.exe  |
   |       Valeur DSCP       | REG_SZ |     46      |
   |        IP locale        | REG_SZ |     \*      |
   | Longueur du préfixe IP local | REG_SZ |     \*      |
   |       Port local       | REG_SZ | 50000-50019 |
   |        Protocole        | REG_SZ |     \*      |
   |       Adresse IP distante        | REG_SZ |     \*      |
   |    Préfixe d’adresse IP distante    | REG_SZ |     \*      |
   |      Port distant       | REG_SZ |     \*      |
   |     Taux de limitation      | REG_SZ |     minute      |
   | | | |

1. Vérifiez que la valeur de l’entrée de nom d’application est correcte pour le client que vous utilisez et vérifiez que la valeur DSCP et les entrées de port local reflètent les paramètres de l’objet de stratégie de groupe.


## <a name="related-topics"></a>Voir aussi

[Mise en œuvre de la qualité de service (QoS) dans teams](QoS-in-Teams.md)