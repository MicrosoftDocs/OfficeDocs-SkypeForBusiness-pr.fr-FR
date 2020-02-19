---
title: Configuration d’une stratégie de qualité de service pour vos serveurs Edge A/V
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a Quality of Service policy for your A/V Edge Servers
ms:assetid: 119ee1f5-45b9-40ba-98e5-c694dd2fc5c2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204681(v=OCS.15)
ms:contentKeyID: 48183444
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b75e6094fd7d84e086e31bbc4535faf0df84155
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134980"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-a-quality-of-service-policy-for-your-av-edge-servers-in-lync-server-2013"></a>Configuration d’une stratégie de qualité de service pour vos serveurs Edge A/V dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-19_

En plus de créer des stratégies de qualité de service pour vos serveurs de conférence, d’application et de médiation, vous devez également créer des stratégies audio et vidéo pour le côté interne de vos serveurs Edge A/V. Toutefois, les stratégies utilisées sur vos serveurs Edge sont différentes des stratégies utilisées sur vos serveurs de conférence, d’application et de médiation. Pour les serveurs de conférence, d’application et de médiation, vous avez spécifié une plage de ports sources ; avec des serveurs Edge, vous devez spécifier une plage de ports de destination. Pour cette raison, vous ne pouvez pas simplement appliquer les stratégies QoS serveur de conférence, d’application et de médiation à vos serveurs Edge : ces stratégies ne fonctionneront tout simplement pas. Au lieu de cela, vous devez créer de nouvelles stratégies et appliquer ces stratégies à vos serveurs Edge uniquement.

La procédure suivante décrit le processus de création d’objets de stratégie de groupe Active Directory qui peuvent être utilisés pour gérer la qualité de service sur les serveurs Edge. Bien entendu, il est possible que vos serveurs Edge soient des serveurs autonomes qui n’ont pas de comptes Active Directory. Si c’est le cas, vous pouvez utiliser la stratégie de groupe locale au lieu de la stratégie de groupe Active Directory : la seule différence réside dans le fait que vous devez créer ces stratégies locales à l’aide de l’éditeur de stratégie de groupe local et créer un même ensemble de stratégies sur chaque serveur Edge. Pour démarrer l’éditeur de stratégie de groupe local sur un serveur Edge, procédez comme suit :

1.  Cliquez sur **Démarrer**, puis sur **Exécuter**.

2.  Dans la boîte de dialogue **exécuter** , tapez **gpedit. msc** , puis appuyez sur entrée.

Si vous créez des stratégies basées sur Active Directory, vous devez ouvrir une session sur un ordinateur sur lequel la gestion des stratégies de groupe a été installée. Dans ce cas, ouvrez gestion des stratégies de groupe (cliquez sur **Démarrer**, pointez sur **Outils d’administration**, puis cliquez sur **gestion des stratégies de groupe**), puis effectuez les étapes suivantes :

1.  Dans la gestion des stratégies de groupe, accédez au conteneur dans lequel la nouvelle stratégie doit être créée. Par exemple, si tous vos ordinateurs Lync Server se trouvent dans une unité d’organisation nommée Lync Server, la nouvelle stratégie doit être créée dans l’unité d’organisation Lync Server.

2.  Cliquez avec le bouton droit sur le conteneur approprié, puis cliquez sur **Créer un objet GPO dans ce domaine, et le lier ici**.

3.  Dans la boîte de dialogue **Nouvel objet GPO**, tapez le nom du nouvel objet de stratégie de groupe dans la zone **Nom** (par exemple, **Audio Lync Server**), puis cliquez sur **OK**.

4.  Cliquez avec le bouton droit sur la stratégie nouvellement créée, puis cliquez sur **Modifier**.

À partir de là, le processus est identique, qu’il s’agisse de la création d’une stratégie Active Directory ou d’une stratégie locale :

1.  Dans l’éditeur de gestion des stratégies de groupe ou l’éditeur de stratégie de groupe local, développez **Configuration ordinateur**, **stratégies**, **Paramètres Windows**, cliquez avec le bouton droit sur **QoS basée**sur la stratégie, puis cliquez sur **créer une stratégie**.

2.  Dans la boîte de dialogue **QoS basée sur la stratégie**, dans la page d’accueil, tapez le nom de la nouvelle stratégie (par exemple, **Audio Lync Server**) dans la zone **Nom**. Sélectionnez **Spécifier la valeur DSCP** et indiquez la valeur **46**. Laissez la case à cocher **Spécifier le taux d’accélération en sortie** désactivée, puis cliquez sur **Suivant**.

3.  Dans la page suivante, assurez-vous que **Toutes les applications** est sélectionné, puis cliquez sur **Suivant**. Ce paramètre indique au réseau de rechercher tous les paquets dont le marquage DSCP est de 46, pas seulement les paquets créés par une application spécifique.

4.  Sur la troisième page, assurez-vous que **toutes les adresses IP source** et **toute adresse IP de destination** sont sélectionnées, puis cliquez sur **suivant**. Ces deux paramètres permettent que tous les paquets soient gérés quel que soit l’ordinateur (adresse IP) qui a envoyé ces paquets et l’ordinateur (adresse IP) qui les reçoit.

5.  Page quatre, sélectionnez **TCP et UDP** dans la liste déroulante **Sélectionnez le protocole auquel s’applique cette stratégie de QoS**. Le protocole TCP (Transmission Control Protocol) et UDP (User Datagram Protocol) sont les deux protocoles réseau les plus couramment utilisés par Lync Server et ses applications clientes.

6.  Sous le titre **Spécifiez le numéro de port de destination**, sélectionnez **à partir de ce port ou cette plage de destination**. Dans la zone de texte correspondante, tapez la plage de ports réservée pour les transmissions audio. Par exemple, si vous avez réservé les ports 49152 via les ports 57500 pour le trafic audio, entrez ensuite la plage de ports au format suivant : **49152:57500**. Cliquez sur**Terminer**.

Une fois que vous avez créé la stratégie de QoS pour le trafic audio, vous devez créer une deuxième stratégie pour le trafic vidéo. Pour créer une stratégie pour la vidéo, suivez la procédure indiquée pour l’audio, et remplacez les éléments suivants :

  - Utilisez un nom de stratégie différent et unique (par exemple, **Vidéo Lync Server**).

  - Attribuez à la valeur DSCP la valeur **34** au lieu de 46. (Notez que vous n’êtes pas obligé d’attribuer la valeur 34 à la valeur DSCP. Le seul impératif est d’utiliser une valeur DSCP pour la vidéo différente de celle utilisée pour l’audio).

  - Utilisez la plage de ports configurée précédemment pour le trafic vidéo. Par exemple, si vous avez réservé les ports 57501 à 65535 pour la vidéo, définissez la plage de ports comme ceci : **57501:65535**. Une fois encore, la plage de ports de destination doit être configurée.

Si vous décidez de créer une stratégie pour gérer le trafic de partage d’application, vous devez créer une troisième stratégie en effectuant les substitutions suivantes :

  - Utilisez un nom de stratégie différent et unique (par exemple, **Partage d’application Lync Server**).

  - Attribuez à la valeur DSCP la valeur **24** au lieu de 46. (Là encore, vous n’êtes pas obligé d’attribuer la valeur 24 à la valeur DSCP. Le seul impératif est d’utiliser une valeur DSCP pour le partage d’application différente de celle utilisée pour l’audio ou la vidéo).

  - Utilisez la plage de ports configurée précédemment pour le trafic vidéo. Par exemple, si vous avez réservé les ports 40803 à 49151 pour le partage d’application, définissez la plage de ports comme ceci : **40803:49151**.

Les nouvelles stratégies que vous avez créées ne prendront effet qu’après l’actualisation de la stratégie de groupe sur vos serveurs Edge. Bien que la stratégie de groupe s’actualise périodiquement, vous pouvez forcer une actualisation immédiate en utilisant la commande suivante sur les ordinateurs sur lesquels la stratégie de groupe doit être actualisée :

    Gpudate.exe /force

Cette commande peut être exécutée à partir de Lync Server ou de n’importe quelle fenêtre de commande exécutée sous les informations d’identification d’administrateur. Pour exécuter une fenêtre de commande avec des droits d’administrateur, cliquez sur **Démarrer**, cliquez avec le bouton droit sur **Invite de commandes**, puis cliquez sur **Exécuter en tant qu’administrateur**. Notez que vous devrez peut-être redémarrer le serveur Edge même après avoir exécuté gpudate. exe.

Pour vous assurer que les paquets réseau sont bien marqués avec la valeur DSCP appropriée, vous devez également créer une entrée de Registre sur chaque ordinateur. Pour cela, procédez comme suit :

1.  Pour ce faire, cliquez sur **Démarrer**, puis sur **Exécuter**.

2.  Dans la boîte de dialogue **Exécuter**, tapez **regedit**, puis appuyez sur Entrée.

3.  Dans l’éditeur du Registre, développez **HKEY\_local\_machine**, **System**, **CurrentControlSet**, **services**, puis **tcpip**.

4.  Cliquez avec le bouton droit sur **Tcpip**, pointez sur **Nouveau**, puis cliquez sur **Clé**. Une fois la clé de Registre créée, tapez **QoS**, puis appuyez sur Entrée pour renommer la clé.

5.  Cliquez avec le bouton droit sur **QoS**, pointez sur **Nouveau**, puis cliquez sur **Valeur chaîne**. Une fois la clé de Registre créée, tapez **Ne pas utiliser NLA**, puis appuyez sur Entrée pour renommer la clé.

6.  Double-cliquez sur **Ne pas utiliser NLA**. Dans la boîte de dialogue **Modification de la chaîne**, tapez **1** dans la zone **Données de la valeur**, puis cliquez sur **OK**.

7.  Fermez l’Éditeur du Registre, puis redémarrez votre ordinateur.

</div>

<span> </span>

</div>

</div>

</div>

