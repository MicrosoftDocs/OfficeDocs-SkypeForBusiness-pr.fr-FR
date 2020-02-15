---
title: 'Lync Server 2013 : configuration des stratégies de qualité de service pour les clients s’exécutant sur Windows 7 ou Windows 8'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Quality of Service policies for clients running on Windows 7 or Windows 8
ms:assetid: efff2b98-b3fb-4183-a4f0-329a9105ce2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205371(v=OCS.15)
ms:contentKeyID: 48185785
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05835b74f12d5e2d28036b100fd84f207a64e67c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046087"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-quality-of-service-policies-in-lync-server-2013-for-clients-running-on-windows-7-or-windows-8"></a>Configuration des stratégies de qualité de service dans Lync Server 2013 pour les clients s’exécutant sur Windows 7 ou Windows 8

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2016-03-29_

En plus de spécifier des plages de ports pour les clients Lync, vous devez également créer des stratégies de qualité de service distinctes qui seront appliquées aux ordinateurs clients. (Les stratégies de qualité de service créées pour les serveurs de conférence, d’application et de médiation ne doivent pas être appliquées aux ordinateurs clients.) Ces informations s’appliquent uniquement aux ordinateurs exécutant le client Lync 2013 et Windows 7 ou Windows 8.

L’exemple suivant utilise cet ensemble de plages de ports pour créer une stratégie audio et une stratégie vidéo :


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Type de trafic client</th>
<th>Démarrage du port</th>
<th>Plage de ports</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Audio</p></td>
<td><p>50020</p></td>
<td><p>vingtaine</p></td>
</tr>
<tr class="even">
<td><p>Vidéo</p></td>
<td><p>58000</p></td>
<td><p>vingtaine</p></td>
</tr>
<tr class="odd">
<td><p>Partage d'application</p></td>
<td><p>42000</p></td>
<td><p>vingtaine</p></td>
</tr>
<tr class="even">
<td><p>Transfert de fichiers</p></td>
<td><p>42020</p></td>
<td><p>vingtaine</p></td>
</tr>
</tbody>
</table>


Pour créer une stratégie audio de qualité de service pour les ordinateurs Windows 7 ou Windows 8, connectez-vous d’abord à un ordinateur sur lequel la gestion des stratégies de groupe a été installée. Ouvrez gestion des stratégies de groupe (cliquez sur **Démarrer**, pointez sur **Outils d’administration**, puis cliquez sur **gestion des stratégies de groupe**), puis effectuez la procédure suivante :

1.  Dans la gestion des stratégies de groupe, accédez au conteneur dans lequel la nouvelle stratégie doit être créée. Par exemple, si tous vos ordinateurs clients se trouvent dans une unité d’organisation nommée clients, la nouvelle stratégie doit être créée dans l’unité d’organisation cliente.

2.  Cliquez avec le bouton droit sur le conteneur approprié, puis cliquez sur **Créer un objet GPO dans ce domaine, et le lier ici**.

3.  Dans la boîte de dialogue **nouvel objet GPO** , tapez un nom pour le nouvel objet de stratégie de groupe dans la zone **nom** (par exemple, **Lync audio**), puis cliquez sur **OK**.

4.  Cliquez avec le bouton droit sur la stratégie nouvellement créée, puis cliquez sur **Modifier**.

5.  Dans l’Éditeur de gestion des stratégies de groupe, développez **Configuration ordinateur**, **Stratégies**, **Paramètres Windows**, cliquez avec le bouton droit sur **QoS basée sur la stratégie**, puis cliquez sur **Créer une nouvelle stratégie**.

6.  Dans la boîte de dialogue **QoS basée** sur la stratégie, dans la page d’accueil, tapez un nom pour la nouvelle stratégie (par exemple, **Lync audio**) dans la zone **nom** . Sélectionnez **Spécifier la valeur DSCP** et indiquez la valeur **46**. Laissez la case à cocher **Spécifier le taux d’accélération en sortie** désactivée, puis cliquez sur **Suivant**.

7. Sur la page suivante, sélectionnez **uniquement les applications avec ce nom d’exécutable** et entrez le nom **Lync. exe**, puis cliquez sur **suivant**. Ce paramètre indique à la stratégie de ne classer que le trafic correspondant à partir du client Lync.

8.  Sur la troisième page, assurez-vous que **toutes les adresses IP source** et **toute adresse IP de destination** sont sélectionnées, puis cliquez sur **suivant**. Ces deux paramètres permettent que tous les paquets soient gérés quel que soit l’ordinateur (adresse IP) qui a envoyé ces paquets et l’ordinateur (adresse IP) qui les reçoit.

9.  Page quatre, sélectionnez **TCP et UDP** dans la liste déroulante **Sélectionnez le protocole auquel s’applique cette stratégie de QoS**. Le protocole TCP (Transmission Control Protocol) et UDP (User Datagram Protocol) sont les deux protocoles réseau les plus couramment utilisés par Lync Server et ses applications clientes.

10. Sous le titre **Spécifiez le numéro de port source**, sélectionnez **À partir de ce port ou plage source**. Dans la zone de texte correspondante, tapez la plage de ports réservée pour les transmissions audio. Par exemple, si vous avez réservé les ports 50020 via les ports 50039 pour le trafic audio, entrez la plage de ports au format suivant : **50020:50039**. Cliquez sur**Terminer**.

Une fois que vous avez créé la stratégie de qualité de service pour l’audio, vous devez créer une deuxième stratégie pour la vidéo. Pour créer une stratégie pour la vidéo, suivez la procédure indiquée pour l’audio, et remplacez les éléments suivants :

  - Utilisez un nom de stratégie différent (et unique) (par exemple, **vidéo Lync**).

  - Attribuez à la valeur DSCP la valeur **34** au lieu de 46. (Comme indiqué précédemment, il n’est pas nécessaire d’utiliser la valeur DSCP 34 ; vous devez simplement affecter une valeur DSCP différente de celle utilisée pour l’audio.)

  - Utilisez la plage de ports configurée précédemment pour le trafic vidéo. Par exemple, si vous avez réservé les ports 58000 à 58019 pour la vidéo, définissez la plage de ports comme suit : **58000:58019**.

Si vous décidez de créer une stratégie pour gérer le trafic du partage d’application, procédez comme suit :

  - Utilisez un nom de stratégie différent et unique (par exemple, **Partage d’application Lync Server**).

  - Attribuez à la valeur DSCP la valeur **24** au lieu de 46. (Encore une fois, cette valeur ne doit pas être égale à 24 ; elle doit simplement être différente des valeurs DSCP utilisées pour l’audio et la vidéo.)

  - Utilisez la plage de ports configurée précédemment pour le trafic vidéo. Par exemple, si vous avez réservé les ports 42000 à 42019 pour le partage d’application, définissez la plage de ports comme suit : **42000:42019**.

Pour une stratégie de transfert de fichiers :

  - Utilisez un nom de stratégie différent (et unique) (par exemple, **transferts de fichiers Lync Server**).

  - Définissez la valeur DSCP sur **14**. (Encore une fois, cette valeur ne doit pas être 14 ; elle doit simplement être un code DSCP unique.)

  - Utiliser la plage de ports précédemment configurée pour l’application. Par exemple, si vous avez réservé les ports 42020 à 42039 pour le partage d’application, définissez la plage de ports comme suit : **42020:42039**.

Les nouvelles stratégies que vous avez créées ne prendront effet qu’après l’actualisation de la stratégie de groupe sur vos ordinateurs clients. Bien que la stratégie de groupe s’actualise périodiquement, vous pouvez forcer une actualisation immédiate en utilisant la commande suivante sur les ordinateurs sur lesquels la stratégie de groupe doit être actualisée :

    Gpudate.exe /force

Cette commande peut être exécutée à partir de n’importe quelle fenêtre de commande exécutée sous les informations d’identification d’administrateur. Pour exécuter une fenêtre de commande avec des droits d’administrateur, cliquez sur **Démarrer**, cliquez avec le bouton droit sur **Invite de commandes**, puis cliquez sur **Exécuter en tant qu’administrateur**.

Gardez à l’esprit que ces stratégies doivent être ciblées vers vos ordinateurs clients. Elles ne doivent pas être appliquées aux serveurs exécutant Lync Server.

Pour vous assurer que les paquets réseau sont bien marqués avec la valeur DSCP appropriée, vous devez également créer une entrée de Registre sur chaque ordinateur. Pour cela, procédez comme suit :

1.  Pour ce faire, cliquez sur **Démarrer**, puis sur **Exécuter**.

2.  Dans la boîte de dialogue **Exécuter**, tapez **regedit**, puis appuyez sur Entrée.

3.  Dans l’éditeur du Registre, développez **HKEY\_local\_machine**, **System**, **CurrentControlSet**, **services**, puis **tcpip**.

4.  Cliquez avec le bouton droit sur **Tcpip**, pointez sur **Nouveau**, puis cliquez sur **Clé**. Une fois la clé de Registre créée, tapez **QoS**, puis appuyez sur Entrée pour renommer la clé.

5.  Cliquez avec le bouton droit sur **QoS**, pointez sur **Nouveau**, puis cliquez sur **Valeur chaîne**. Une fois la clé de Registre créée, tapez **Ne pas utiliser NLA**, puis appuyez sur Entrée pour renommer la clé.

6.  Double-cliquez sur **ne pas utiliser NLA**. Dans la boîte de dialogue **Modification de la chaîne**, tapez **1** dans la zone **Données de la valeur**, puis cliquez sur **OK**.

7.  Fermez l’Éditeur du Registre, puis redémarrez votre ordinateur.

<div>

## <a name="configuring-quality-of-service-on-computers-with-multiple-network-adapters"></a>Configuration de la qualité de service sur des ordinateurs avec plusieurs cartes réseau

Si vous disposez d’un ordinateur doté de plusieurs cartes réseau, vous pouvez parfois rencontrer des problèmes lorsque des valeurs DSCP apparaissent sous la forme 0x00 au lieu de la valeur configurée. Cela se produit généralement sur les ordinateurs sur lesquels une ou plusieurs cartes réseau ne peuvent pas accéder à votre domaine Active Directory (par exemple, si ces adaptateurs sont utilisés pour un réseau privé). Dans ce cas, les valeurs DSCP seront balisées pour les cartes qui peuvent accéder au domaine, mais elles ne seront pas balisées pour les cartes qui ne peuvent pas accéder au domaine.

Si vous souhaitez marquer les valeurs DSCP pour toutes les cartes réseau d’un ordinateur, y compris les adaptateurs qui n’ont pas accès à votre domaine, vous devez ajouter et configurer une valeur dans le registre. Pour cela, effectuez la procédure suivante :

1.  Cliquez sur **Démarrer**, puis sur **Exécuter**.

2.  Dans la boîte de dialogue **Exécuter**, tapez **regedit**, puis appuyez sur Entrée.

3.  Dans l’éditeur du Registre, développez **HKEY\_local\_machine**, **System**, **CurrentControlSet**, **services**, puis **tcpip**.

4.  Si vous ne voyez pas de clé de registre intitulée **QoS** , cliquez avec le bouton droit sur **tcpip**, pointez sur **nouveau**, puis cliquez sur **clé**. Une fois la nouvelle clé créée, tapez **QoS** , puis appuyez sur entrée pour renommer la clé.

5.  Cliquez avec le bouton droit sur **QoS**, pointez sur **Nouveau**, puis cliquez sur **Valeur chaîne**. Une fois la clé de Registre créée, tapez **Ne pas utiliser NLA**, puis appuyez sur Entrée pour renommer la clé.

6.  Double-cliquez sur **ne pas utiliser NLA**. Dans la boîte de dialogue **Modification de la chaîne**, tapez **1** dans la zone **Données de la valeur**, puis cliquez sur **OK**.

Après avoir créé et configuré la nouvelle valeur de Registre, vous devez redémarrer votre ordinateur afin que les modifications soient prises en compte.

</div>

</div>

<span> </span>

</div>

</div>

</div>

