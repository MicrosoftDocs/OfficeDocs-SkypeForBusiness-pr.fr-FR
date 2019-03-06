---
title: Implémenter la qualité de service dans Microsoft Teams
author: jambirk
ms.author: jambirk
manager: Serdars
ms.date: 2/17/2019
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Implémentez la qualité de Service (QoS) pour les clients Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: b1f80ede0432c3666a1974b1e0c8d7fa3dc2bbfc
ms.sourcegitcommit: d90beb625c2d12616fb9aee39b6dd1c2d4c12947
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/05/2019
ms.locfileid: "30408266"
---
# <a name="set-qos-on-windows-clients"></a>Jeu de QoS sur les clients Windows

Vous pouvez utiliser QoS basée sur les stratégies au sein de la stratégie de groupe pour définir la plage de ports source pour la valeur DSCP prédéfinie dans le client d’équipes. Les plages de ports spécifiés dans le tableau suivant sont un point de départ pour créer une stratégie pour chaque charge de travail.

_Recommandé de plages de ports initiale_

Type de trafic multimédia| Plage de ports client source |Protocole|Valeur DSCP|Classe DSCP|
|:--- |:--- |:--- |:--- |:--- |
|Audio| 50 000 – 50,019|TCP/UDP|46|Acheminement accéléré (EF)|
|Vidéo| 50,020 – 50,039|TCP/UDP|34|Acheminement assuré (AF41)|
|Partage d’application/écran| 50,040 – 50,059|TCP/UDP|18|Assured Forwarding (AF21)|
| | | | |

Dans la mesure du possible, configurez les paramètres de QoS basée sur la stratégie au sein d’un objet de stratégie de groupe. Les étapes suivantes sont très similaires à la [Configuration des plages de ports et une stratégie de qualité de Service pour vos clients sur Skype pour Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), qui comprend des informations supplémentaires qui ne peuvent pas être nécessaires.

Pour créer une stratégie audio QoS pour les ordinateurs Windows 10 AccountManagement liés, ouvrez une session un ordinateur sur lequel la gestion des stratégies de groupe a été installée. Ouvrez Gestion des stratégies de groupe (cliquez sur Démarrer, pointez sur Outils d’administration, puis cliquez sur gestion des stratégies de groupe), puis suivez les étapes suivantes :

1. Dans Gestion de stratégie de groupe, recherchez le conteneur où la nouvelle stratégie doit être créée. Par exemple, si tous vos ordinateurs clients se trouvent dans une unité d’organisation nommée **Clients**, la nouvelle stratégie doit être créée en l’unité d’organisation du Client.

2. Cliquez sur le conteneur approprié, puis cliquez sur **créer un objet GPO dans ce domaine et le lier ici**.

3. Dans la boîte de dialogue **Nouvel objet GPO** , tapez un nom pour le nouvel objet de stratégie de groupe dans la zone **nom** , puis cliquez sur **OK**.

4. Avec le bouton droit de la stratégie nouvellement créée, puis cliquez sur **Modifier**.

5. Dans l’éditeur de gestion de stratégie de groupe, développez **Configuration ordinateur**, développez **Paramètres Windows**, avec le bouton droit **QoS basée sur la stratégie**, puis cliquez sur **créer une nouvelle stratégie**.

6. Dans la boîte de dialogue **QoS basée** sur la page de démarrage, tapez un nom pour la nouvelle stratégie dans la zone **nom** . Sélectionnez **Spécifier la valeur DSCP** , définissez la valeur à **46**. Laissez **Spécifier le taux d’accélération sortant** non sélectionné, puis cliquez sur **suivant**.

7. Dans la page suivante, sélectionnez **uniquement les applications portant ce nom exécutable** et entrez le nom **Teams.exe**, puis cliquez sur **suivant**. Ce paramètre indique à la stratégie pour définir la priorité uniquement le trafic correspondant à partir du client équipes.

8. Dans la troisième page, assurez-vous que **toute adresse IP source** et **n’importe quelle adresse IP de destination** sont sélectionnés, puis cliquez sur **suivant**. Ces deux paramètres de vous assurer que les paquets sont gérés indépendamment de l’ordinateur (adresse IP) envoyé les paquets et l’ordinateur (adresse IP) reçoit les paquets.

9. Sur la page quatre, sélectionnez **TCP et UDP** dans la liste déroulante **Sélectionnez le protocole d’à que cette stratégie de QoS s’applique** . TCP (Transmission Control Protocol) et UDP (User Datagram Protocol) sont les deux protocoles réseau les plus couramment utilisées.

10. Sous le titre, **Spécifiez le numéro de port source**, sélectionnez **à partir de ce port source ou de la plage**. Dans la zone de texte correspondante, tapez la plage de ports réservée pour les transmissions audio. Par exemple, si vous réservé ports 50000 par le biais de ports 50019 pour le trafic audio, entrez la plage de ports à l’aide de ce format : **50000:50019**. Cliquez sur **Terminer**.

11. Répétez les étapes 5 à 10 pour créer des stratégies pour la vidéo et l’Application/partage du bureau, en remplaçant les valeurs appropriées dans les étapes 6 et 10.

Les nouvelles stratégies que vous avez créé ne prennent effet tant que la stratégie de groupe a été actualisée sur vos ordinateurs clients. Bien que la stratégie de groupe est actualisée régulièrement sur son propre, vous pouvez forcer une actualisation immédiate en suivant ces étapes :

1. Sur chaque ordinateur pour lequel vous voulez actualiser la stratégie de groupe, ouvrez une console de commande. Assurez-vous que la console de commande est définie sur Exécuter en tant qu’administrateur.

2. À l’invite de commandes, entrez

   ``` powershell
    gpupdate.exe /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a>Vérifier le marquage DSCP dans l’objet de stratégie de groupe

Pour vérifier que les valeurs de l’objet de stratégie de groupe ont été définies, procédez comme suit.

1. Ouvrez une console de commande. Assurez-vous que la console de commande est définie sur Exécuter en tant qu’administrateur.

2. À l’invite de commandes, entrez :

   ``` powershell
   gpresult /R > gp.txt
   ```

   Cela générer un rapport et envoyez-le à un fichier texte nommé gp.txt. Vous pouvez également entrer la commande suivante pour produire les mêmes données dans un rapport HTML plus lisible nommé gp.html :

   ``` powershell
   gpresult /H >gp.html
   ```

   ![Capture d’écran de la fenêtre de console exécutant la commande gpresult.] (media/Qos-in-Teams-Image3.png "Capture d’écran de la fenêtre de console exécutant la commande gpresult.")

3. Dans le fichier généré, recherchez l’en-tête **Appliqué des objets de stratégie de groupe** et vérifiez que les noms des objets de stratégie de groupe créés précédemment sont dans la liste des stratégies appliquées.

4. Ouvrez l’Éditeur du Registre et accédez à :

   HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\QoS\

   Vérifiez les valeurs pour les entrées de Registre répertoriées dans le tableau 4.

   _Le tableau 4. Valeurs des entrées du Registre Windows pour QoS_

   |          Nom          |  Type  |    Données     |
   |         :---:          |:---:   |    :---:    |
   |    Nom de l’application    | REG_SZ |  Teams.exe  |
   |       Valeur DSCP       | REG_SZ |     46      |
   |        Adresse IP locale        | REG_SZ |     \*      |
   | Longueur du préfixe de l’adresse IP locale | REG_SZ |     \*      |
   |       Port local       | REG_SZ | 50000-50019 |
   |        Protocole        | REG_SZ |     \*      |
   |       Adresse IP distante        | REG_SZ |     \*      |
   |    Préfixe de l’adresse IP distante    | REG_SZ |     \*      |
   |      Port distant       | REG_SZ |     \*      |
   |     Taux d’accélération      | REG_SZ |     -1      |

5. Vérifiez que la valeur de l’entrée de nom de l’Application est correcte pour le client que vous utilisez, puis vérifiez que la valeur DSCP et le Port Local entrées reflètent les paramètres de l’objet de stratégie de groupe.
