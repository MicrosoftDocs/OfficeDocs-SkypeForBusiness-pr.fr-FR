---
title: Implémenter la qualité de service dans Microsoft Teams
author: jambirk
ms.author: jambirk
manager: Serdars
ms.date: 2/17/2019
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Implémenter la qualité de service (QoS) pour les clients Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 28e6664fa43819493e5b9e02d182bcec44f00905
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37572562"
---
# <a name="set-qos-on-windows-clients"></a>Définir la qualité de service sur les clients Windows

Vous pouvez utiliser la QoS basée sur une stratégie dans une stratégie de groupe pour définir la plage de ports sources pour la valeur DSCP prédéfinie dans le client Teams. Les plages de port spécifiées dans le tableau suivant constituent un point de départ pour créer une stratégie pour chaque charge de travail.

_Plages de port initiales recommandées_

Type de trafic multimédia| Plage de ports sources du client |Protocole|Valeur DSCP|Classe DSCP|
|:--- |:--- |:--- |:--- |:--- |
|Audio| 50000 – 50019|TCP/UDP|46|Acheminement accéléré (EF)|
|Vidéo| 50,020 – 50039|TCP/UDP|34|Acheminement assuré (AF41)|
|Partage d’écran ou d’application| 50,040 – 50059|TCP/UDP|19|Transfert assuré (AF21)|
| | | | |

Dans la mesure du possible, vous pouvez configurer les paramètres de QoS basée sur une stratégie au sein d’un objet de stratégie de groupe. Les étapes suivantes sont similaires à la [configuration de plages de ports et d’une politique de qualité de service pour vos clients sur Skype entreprise Server](https://docs.microsoft.com/SkypeForBusiness/manage/network-management/qos/configuring-port-ranges-for-your-skype-clients#configure-quality-of-service-policies-for-clients-running-on-windows-10), qui comporte des informations supplémentaires qui peuvent ne pas être nécessaires.

Pour créer une stratégie audio QoS pour des ordinateurs Windows 10 liés à un domaine, vous devez d’abord vous connecter à un ordinateur sur lequel est installée la gestion des stratégies de groupe. Ouvrez gestion des stratégies de groupe (cliquez sur Démarrer, pointez sur outils d’administration, cliquez sur gestion des stratégies de groupe), puis procédez comme suit :

1. Dans gestion des stratégies de groupe, recherchez le conteneur dans lequel la nouvelle stratégie doit être créée. Par exemple, si tous vos ordinateurs clients se trouvent dans une unité d’organisation nommée **clients**, la nouvelle stratégie doit être créée dans l’unité d’organisation cliente.

2. Cliquez avec le bouton droit sur le conteneur approprié, puis cliquez sur **créer un objet de stratégie de groupe dans ce domaine et liez-le ici**.

3. Dans la boîte de dialogue **nouvel objet GPO** , entrez un nom pour le nouvel objet de stratégie de groupe dans la zone **nom** , puis cliquez sur **OK**.

4. Cliquez avec le bouton droit sur la stratégie que vous venez de créer, puis cliquez sur **modifier**.

5. Dans l’éditeur de gestion des stratégies de groupe, développez **Configuration ordinateur**, développez **Paramètres Windows**, cliquez avec le bouton droit sur **QoS basée sur une stratégie**, puis cliquez sur **créer une nouvelle stratégie**.

6. Dans la boîte de dialogue **QoS basée sur une stratégie** , dans la page d’ouverture, tapez un nom pour la nouvelle stratégie dans la zone **nom** . Sélectionnez **spécifier la valeur DSCP** et définissez la valeur sur **46**. Laissez l’option **spécifier le taux de limitation en sortie** non sélectionnée, puis cliquez sur **suivant**.

7. Sur la page suivante, sélectionnez **uniquement les applications avec ce nom d’exécutable** et entrez le nom **Teams. exe**, puis cliquez sur **suivant**. Ce paramètre indique à la stratégie de classer uniquement le trafic correspondant du client Teams.

8. Sur la troisième page, assurez-vous que toutes les **adresses IP source** et **adresse IP de destination** sont sélectionnées, puis cliquez sur **suivant**. Ces deux paramètres garantissent le fonctionnement de la gestion des paquets indépendamment de l’ordinateur (adresse IP) ayant envoyé les paquets et de l’ordinateur (adresse IP) recevant les paquets.

9. Dans la page 4, sélectionnez **TCP et UDP** dans la liste déroulante **Sélectionner le protocole que cette stratégie de QoS applique à** . TCP (Transmission Control Protocol) et UDP (User Datagram Protocol) sont les deux protocoles réseau les plus fréquemment utilisés.

10. Sous le titre **Spécifiez le numéro de port source**, sélectionnez **à partir de ce port ou plage de sources**. Dans la zone texte de l’accompagnement, tapez la plage de ports réservée aux transmissions audio. Par exemple, si vous avez réservé ports 50000 via ports 50019 pour le trafic audio, entrez la plage de ports à l’aide du format suivant : **50000:50019**. Cliquez sur **Terminer**.

11. Répétez les étapes 5-10 pour créer des stratégies pour la vidéo et le partage de bureau et d’application

Les nouvelles stratégies que vous avez créées ne prennent effet qu’après la réactualisation de la stratégie de groupe sur les ordinateurs clients. Bien que la stratégie de groupe s’actualise périodiquement, vous pouvez forcer une actualisation immédiate en procédant comme suit :

1. Sur chaque ordinateur sur lequel vous souhaitez actualiser une stratégie de groupe, ouvrez une console de commandes. Vérifiez que la console de commandes est définie sur Exécuter en tant qu’administrateur.

2. À l’invite de commandes, entrez

   ``` powershell
    gpupdate.exe /force
   ```

## <a name="verify-dscp-markings-in-the-group-policy-object"></a>Vérifier les marquages DSCP dans l’objet de stratégie de groupe

Pour vérifier que les valeurs de l’objet de stratégie de groupe ont été définies, procédez comme suit.

1. Ouvrez une console de commandes. Vérifiez que la console de commandes est définie sur Exécuter en tant qu’administrateur.

2. À l’invite de commandes, entrez :

   ``` powershell
   gpresult /R > gp.txt
   ```

   Cette opération génère un rapport et l’envoie à un fichier texte nommé GP. txt. Vous pouvez également entrer la commande suivante pour générer les mêmes données dans un rapport HTML plus lisible nommé GP. html :

   ``` powershell
   gpresult /H >gp.html
   ```

   ![Capture d’écran de la fenêtre de console exécutant la commande Gpresult.](media/Qos-in-Teams-Image3.png "Capture d’écran de la fenêtre de console exécutant la commande Gpresult.")

3. Dans le fichier généré, recherchez le titre **appliqué objets de stratégie de groupe** , puis vérifiez que les noms des objets de stratégie de groupe créés précédemment figurent dans la liste des stratégies appliquées.

4. Ouvrez l’éditeur du Registre et rendez-vous sur :

   HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\QoS\

   Vérifiez les valeurs des entrées de registre indiquées dans le tableau 4.

   _Tableau 4. Valeurs pour les entrées de Registre Windows pour QoS_

   |          Nom          |  Type  |    Données     |
   |         :---:          |:---:   |    :---:    |
   |    Nom de l’application    | REG_SZ |  Teams. exe  |
   |       Valeur DSCP       | REG_SZ |     46      |
   |        IP locale        | REG_SZ |     \*      |
   | Longueur du préfixe IP local | REG_SZ |     \*      |
   |       Port local       | REG_SZ | 50000-50019 |
   |        Protocole        | REG_SZ |     \*      |
   |       Adresse IP distante        | REG_SZ |     \*      |
   |    Préfixe d’adresse IP distante    | REG_SZ |     \*      |
   |      Port distant       | REG_SZ |     \*      |
   |     Taux de limitation      | REG_SZ |     minute      |

5. Vérifiez que la valeur de l’entrée de nom d’application est correcte pour le client que vous utilisez et vérifiez que la valeur DSCP et les entrées de port local reflètent les paramètres de l’objet de stratégie de groupe.
