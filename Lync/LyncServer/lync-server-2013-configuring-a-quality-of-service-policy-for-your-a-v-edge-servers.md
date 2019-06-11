---
title: Configuration d’une stratégie de qualité de service pour vos serveurs Edge A/V
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a Quality of Service policy for your A/V Edge Servers
ms:assetid: 119ee1f5-45b9-40ba-98e5-c694dd2fc5c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204681(v=OCS.15)
ms:contentKeyID: 48183444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58f5bfabfe794ed274d28074aaf162bc715a6ed3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838309"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-quality-of-service-policy-for-your-av-edge-servers-in-lync-server-2013"></a>Configuration d’une stratégie de qualité de service pour vos serveurs Edge A/V dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-19_

Outre la création de stratégies de QoS pour vos serveurs de conférence, d’application et de médiation, vous devez également créer des stratégies audio et vidéo pour le côté interne de vos serveurs de frontière A/V. Toutefois, les stratégies utilisées sur les serveurs de périphérie sont différentes de celles utilisées sur les serveurs de conférences, d’applications et de médiation. Pour les serveurs de conférence, d’application et de médiation, vous avez spécifié une plage de ports sources; Si vous avez un serveur Edge, vous devez spécifier la plage de ports de destination. Pour cette raison, vous ne pouvez pas simplement appliquer les stratégies QoS du serveur Conferencing, d’application et de médiation aux serveurs Edge: ces stratégies ne fonctionneront pas. Au lieu de cela, vous devez créer de nouvelles stratégies et appliquer ces stratégies uniquement aux serveurs Edge.

La procédure suivante décrit le processus de création d’objets de stratégie de groupe Active Directory qui peuvent être utilisés pour gérer la qualité du service sur les serveurs Edge. Bien entendu, il est possible que vos serveurs Edge sont des serveurs autonomes qui ne disposent pas de comptes Active Directory. Si tel est le cas, vous pouvez utiliser une stratégie de groupe locale au lieu de la stratégie de groupe Active Directory: la seule différence réside dans le fait que vous devez créer ces stratégies locales à l’aide de l’éditeur de stratégies de groupe local, et créer individuellement le même ensemble de stratégies sur chaque serveur Edge. Pour démarrer l’éditeur d’une stratégie de groupe locale sur un serveur Edge, procédez comme suit:

1.  Cliquez sur **Démarrer** , puis sur **exécuter**.

2.  Dans la boîte de dialogue **exécuter** , tapez **gpedit. msc** , puis appuyez sur entrée.

Si vous créez des stratégies basées sur Active Directory, vous devez vous connecter à un ordinateur sur lequel est installée la gestion des stratégies de groupe. Dans ce cas, ouvrez gestion des stratégies de groupe (cliquez sur **Démarrer**, pointez sur **Outils d’administration**, puis cliquez sur gestion de la **stratégie de groupe**), puis procédez comme suit:

1.  Dans gestion des stratégies de groupe, recherchez le conteneur dans lequel la nouvelle stratégie doit être créée. Par exemple, si tous vos ordinateurs serveur Lync résident dans une unité d’organisation nommée Lync Server, la nouvelle stratégie doit être créée dans l’unité d’organisation Lync Server.

2.  Cliquez avec le bouton droit sur le conteneur approprié, puis cliquez sur **créer un objet de stratégie de groupe dans ce domaine et associez-le ici**.

3.  Dans la boîte de dialogue **nouvel objet GPO** , entrez le nom du nouvel objet de stratégie de groupe dans la zone **nom** (par exemple, **Lync Server audio**), puis cliquez sur **OK**.

4.  Cliquez avec le bouton droit sur la stratégie que vous venez de créer, puis cliquez sur **modifier**.

À partir de là, le processus est identique, que vous soyez ou non à la création d’une stratégie Active Directory ou d’une stratégie locale:

1.  Dans l’éditeur de gestion des stratégies de groupe ou dans l’éditeur de stratégies de groupe local, développez Configuration de l' **ordinateur**, développez **stratégies**, développez **Paramètres Windows**, cliquez avec le bouton droit sur **QoS basée sur une stratégie**, puis cliquez sur **créer une nouvelle stratégie**.

2.  Dans la boîte de dialogue **QoS basée** sur une stratégie, dans la page d’ouverture, tapez un nom pour la nouvelle stratégie (par exemple, **Lync Server audio**) dans la zone **nom** . Sélectionnez **spécifier la valeur DSCP** et définissez la valeur sur **46**. Laissez l’option **spécifier le taux de limitation en sortie** non sélectionnée, puis cliquez sur **suivant**.

3.  Dans la page suivante, assurez-vous que l’option **toutes les applications** est sélectionnée, puis cliquez sur **suivant**. Ce paramètre indique au réseau de chercher tous les paquets avec un marquage DSCP de 46, pas seulement les paquets créés par une application spécifique.

4.  Sur la troisième page, assurez-vous que toutes les **adresses IP source** et **adresse IP de destination** sont sélectionnées, puis cliquez sur **suivant**. Ces deux paramètres garantissent le fonctionnement de la gestion des paquets indépendamment de l’ordinateur (adresse IP) ayant envoyé ces paquets et de l’ordinateur (adresse IP) recevant ces paquets.

5.  Dans la page 4, sélectionnez **TCP et UDP** dans la liste déroulante **Sélectionner le protocole que cette stratégie de QoS applique à** . TCP (Transmission Control Protocol) et UDP (User Datagram Protocol) sont les deux protocoles réseau les plus fréquemment utilisés par Lync Server et ses applications clientes.

6.  Sous le titre **Spécifiez le numéro de port de destination**, faites votre choix **dans la plage ou le port de destination**. Dans la zone texte de l’accompagnement, tapez la plage de ports réservée aux transmissions audio. Par exemple, si vous avez réservé ports 49152 via ports 57500 pour le trafic audio, entrez la plage de ports à l’aide du format suivant: **49152:57500**. Cliquez sur **Terminer**.

Après avoir créé la stratégie de QoS pour le trafic audio, vous devez créer une seconde stratégie de trafic vidéo. Pour créer une stratégie pour la vidéo, suivez la même procédure que celle que vous avez suivie lors de la création de la stratégie audio, en effectuant les substitutions suivantes:

  - Utilisez un nom de stratégie différent (et unique) (par exemple, **Lync Server Video**).

  - Définissez la valeur DSCP sur **34** au lieu de 46. (Notez que vous n’avez pas besoin d’utiliser une valeur DSCP de 34. La seule condition requise est d’utiliser une autre valeur DSCP pour la vidéo que celle utilisée pour l’audio.

  - Utilisez la plage de ports déjà configurée pour le trafic vidéo. Par exemple, si vous avez réservé ports 57501 à 65535 pour la vidéo, définissez la plage de ports comme suit: **57501:65535**. Là encore, cela doit être configuré comme plage de ports de destination.

Si vous décidez de créer une stratégie de gestion du trafic de partage d’application, vous devez créer une troisième stratégie en effectuant les substitutions suivantes:

  - Utilisez un nom de stratégie différent (et unique) (par exemple, le **partage d’applications serveur Lync**).

  - Définissez la valeur DSCP sur **24** au lieu de 46. (De nouveau, vous n’avez pas besoin d’utiliser une valeur DSCP de 24. La seule condition requise est d’utiliser une autre valeur DSCP pour le partage d’application que celle utilisée pour l’audio ou la vidéo.)

  - Utilisez la plage de ports déjà configurée pour le trafic vidéo. Par exemple, si vous avez réservé ports 40803 à 49151 pour le partage d’application, définissez l’intervalle de ports comme suit: **40803:49151**.

Les nouvelles stratégies que vous avez créées ne sont pas prises en compte tant que la stratégie de groupe n’a pas été actualisée sur votre serveur Edge. Bien que la stratégie de groupe s’actualise périodiquement, vous pouvez forcer une actualisation immédiate en exécutant la commande suivante sur chaque ordinateur dans lequel la stratégie de groupe doit être actualisée:

    Gpudate.exe /force

Vous pouvez exécuter cette commande à partir du serveur Lync ou à partir de n’importe quelle fenêtre de commande qui s’exécute sous informations d’identification d’administrateur. Pour exécuter une fenêtre de commande sous informations d’identification d’administrateur, cliquez sur **Démarrer**, cliquez avec le bouton droit sur **invite de commandes**, puis cliquez sur **exécuter en tant qu’administrateur**. Notez qu’il se peut que vous deviez redémarrer le serveur Edge même après avoir exécuté gpudate. exe.

Pour vous assurer que les paquets réseau sont marqués avec la valeur DSCP appropriée, vous devez également créer une nouvelle entrée de Registre sur chaque ordinateur en suivant la procédure suivante:

1.  Cliquez sur **Démarrer** , puis sur **exécuter**.

2.  Dans la boîte de dialogue **exécuter** , tapez **regedit** , puis appuyez sur entrée.

3.  Dans l’éditeur du Registre, développez l' **ordinateur\_\_local HKEY**, développez **système**, **CurrentControlSet**, développez **services**, puis cliquez sur **tcpip**.

4.  Cliquez avec le bouton droit sur **tcpip**, pointez sur **nouveau**, puis cliquez sur **clé**. Une fois la nouvelle clé de Registre créée, tapez **QoS** , puis appuyez sur entrée pour renommer la clé.

5.  Cliquez avec le bouton droit sur **QoS**, pointez sur **nouveau**, puis cliquez sur **valeur de chaîne**. Après la création de la nouvelle valeur du Registre, tapez **ne pas utiliser NLA** , puis appuyez sur entrée pour renommer la valeur.

6.  Double-cliquez sur **ne pas utiliser NLA**. Dans la boîte de dialogue modification de la **chaîne** , tapez **1** dans la zone données de la **valeur** , puis cliquez sur **OK**.

7.  Fermez l’éditeur du Registre, puis redémarrez votre ordinateur.

</div>

<span> </span>

</div>

</div>

</div>

