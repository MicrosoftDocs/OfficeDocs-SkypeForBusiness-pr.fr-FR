---
title: Implémenter la qualité de service (QoS) dans Microsoft Teams clients
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: Découvrez comment utiliser la qualité de service (QoS) pour optimiser le trafic réseau du client Microsoft Teams bureau.
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
ms.openlocfilehash: c283a66db274bc8723d429631bf265fdb0f5206b
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58606013"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams-clients"></a>Implémenter la qualité de service (QoS) dans Microsoft Teams clients

Vous pouvez utiliser la qualité de service basée sur une stratégie au sein d’une stratégie de groupe pour définir la plage de ports source pour la valeur DSCP prédéfinée dans le client Teams client. Les plages de ports spécifiées dans le tableau suivant sont un point de départ pour créer une stratégie pour chaque charge de travail.

*Tableau 1. Plages de ports initiales recommandées*

|Type de trafic média| Plage de port source du client  |Protocole|Valeur DSCP|Classe DSCP|
|:--- |:--- |:--- |:--- |:--- |
|Audio| Entre 50 000 et 50 019|TCP/UDP|46|Acheminement accéléré (EF)|
|Vidéo| 50 020–50 039|TCP/UDP|34|Acheminement assuré (AF41)|
|Partage d’application/d'écran| 50 040–50 059|TCP/UDP|18|Transfert garanti (AF21)|
| | | | | |

Lorsque possible, configurez les paramètres de QoS basés sur une stratégie dans un objet de stratégie de groupe. Les étapes suivantes sont très semblables à la configuration des plages de ports et à une stratégie de qualité de service pour vos clients sur [Skype Entreprise Server,](/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10)qui présente des détails supplémentaires qui peuvent ne pas être nécessaires.

Pour créer une stratégie audio QoS pour des ordinateurs Windows 10 joints à un domaine, connectez-vous d’abord à un ordinateur sur lequel la gestion des stratégies de groupe a été installée. Ouvrez la gestion des stratégies de groupe (cliquez sur Démarrer, pointez sur Outils d’administration, puis cliquez sur Gestion des stratégies de groupe), puis complétez les étapes suivantes :

1. Dans la gestion des stratégies de groupe, recherchez le conteneur dans lequel la nouvelle stratégie doit être créée. Par exemple, si tous vos ordinateurs clients sont situés dans une ou plusieurs **clients,** la nouvelle stratégie doit être créée dans l’ou Clients.

1. Cliquez avec le bouton droit sur le conteneur approprié, puis cliquez sur Créer un GPO dans ce **domaine, puis lier ici.**

1. Dans la **boîte de dialogue** Nouveau objet de stratégie de groupe, tapez un nom pour le nouvel objet de stratégie de groupe dans la zone Nom, puis cliquez sur **OK.** 

1. Cliquez avec le bouton droit sur la stratégie nouvellement créée, puis cliquez sur **Modifier.**

1. Dans l’Éditeur de gestion des stratégies de groupe, développez **Configuration** ordinateur, développez **Windows Paramètres,** cliquez avec le bouton droit sur **QoS** basé sur une stratégie, puis cliquez sur **Créer une stratégie.**

1. Dans la **boîte de dialogue QoS** basée sur une stratégie, dans la page d’ouverture, tapez le nom de la nouvelle stratégie dans la **zone** Nom. Sélectionnez **Spécifier la valeur DSCP** et définissez la valeur **sur 46.** Laissez **Spécifier le taux d’limitation** sortant non sélectionné, puis cliquez sur **Suivant.**

1. Sur la page suivante, sélectionnez Uniquement les applications avec ce nom **exécutable,** entrez le **Teams.exe,** puis cliquez sur **Suivant.** Ce paramètre indique à la stratégie de ne hiérarchiser que les trafics correspondants en provenance Teams client.

1. Dans la troisième page, assurez-vous que les deux adresses **IP source** et N’importe quelle adresse IP de **destination** sont sélectionnées, puis cliquez sur **Suivant.** Ces deux paramètres assurent la gestion des paquets, quel que soit l’ordinateur (adresse IP) qui a envoyé les paquets et le ou les ordinateurs (adresses IP) qui recevront les paquets.

1. Dans la page 4, sélectionnez TCP et **UDP** dans le protocole Sélectionnez le protocole que cette stratégie **QoS** s’applique à la liste de listes bas. TCP (Transmission Control Protocol) et UDP (User Datagram Protocol) sont les deux protocoles réseau les plus couramment utilisés.

1. Sous **l’en-tête Spécifiez le numéro du port source,** **sélectionnez À partir de ce port ou plage source.** Dans la zone de texte d’accompagnement, tapez la plage de ports réservée aux transmissions audio. Par exemple, si vous avez réservé des ports 50000 à ports 50019 pour le trafic audio, entrez la plage de ports en utilisant ce format : **50000:50019.** Cliquez sur **Terminer**.

1. Répétez les étapes 5 à 10 pour créer des stratégies pour le partage de vidéo et d’application/bureau en remplaçant les valeurs appropriées aux étapes 6 et 10.

Les nouvelles stratégies que vous avez créées ne prennent pas effet tant que la stratégie de groupe n’a pas été actualisée sur vos ordinateurs clients. Bien que la stratégie de groupe soit actualisée régulièrement, vous pouvez forcer une actualisation immédiate en suivant les étapes suivantes :

1. Sur chaque ordinateur pour lequel vous voulez actualiser la stratégie de groupe, ouvrez une invite de commandes en tant qu’administrateur *(exécuter en tant qu’administrateur).*

1. À l’invite de commandes, entrez

   ```console
   gpupdate /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a>Vérifier les marquages DSCP dans l’objet de stratégie de groupe

Pour vérifier que les valeurs de l’objet de stratégie de groupe ont été définies, effectuez les étapes suivantes :

1. Ouvrez une invite de commandes en tant qu’administrateur *(exécuter en tant qu’administrateur).*

1. À l’invite de commandes, entrez

   ```console
   gpresult /R > gp.txt
   ```

   Cela génère un rapport sur les GGP appliqués et l’envoie à un fichier texte nommé *gp.txt.*

   Pour un rapport HTML plus lisible nommé *gp.html,* entrez la commande suivante :

   ```console
   gpresult /H gp.html
   ```

1. Dans le fichier généré, recherchez l’en-tête Objets de stratégie de groupe **appliqués** et vérifiez que les noms des objets de stratégie de groupe créés précédemment figurent dans la liste des stratégies appliquées.

1. Ouvrez l’Éditeur du Registre, puis allez à

   Politiques \_ logicielles LOCALES HKEY pour Microsoft \_ Windows \\ \\ \\ \\ \\ QoS

   Vérifiez les valeurs des entrées de Registre répertoriées dans le tableau 2.

   *Tableau 2. Valeurs des Windows de Registre pour QoS*

   |          Nom          |  Type  |    Données     |
   |         :---:          | :---:  |    :---:    |
   |    Nom de l’application    | REG_SZ |  Teams.exe  |
   |       Valeur DSCP       | REG_SZ |     46      |
   |        Adresse IP locale        | REG_SZ |     \*      |
   | Longueur du préfixe IP local | REG_SZ |     \*      |
   |       Local Port       | REG_SZ | 50000-50019 |
   |        Protocole        | REG_SZ |     \*      |
   |       Adresse IP distante        | REG_SZ |     \*      |
   |    Préfixe IP distant    | REG_SZ |     \*      |
   |      Port distant       | REG_SZ |     \*      |
   |     Limiter les taux      | REG_SZ |     -1      |
   | | | |

1. Vérifiez que la valeur de l’entrée Nom de l’application est correcte pour le client que vous utilisez, et vérifiez que les entrées de port DSCP et de port local reflètent les paramètres dans l’objet de stratégie de groupe.


## <a name="related-topics"></a>Rubriques connexes

[Implémenter la qualité de service (QoS) dans Teams](QoS-in-Teams.md)