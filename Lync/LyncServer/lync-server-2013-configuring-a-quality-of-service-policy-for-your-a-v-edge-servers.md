---
title: Configuration d’une stratégie Qualité de service pour vos serveurs Edge A/V
TOCTitle: Configuration d’une stratégie Qualité de service pour vos serveurs Edge A/V
ms:assetid: 119ee1f5-45b9-40ba-98e5-c694dd2fc5c2
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204681(v=OCS.15)
ms:contentKeyID: 49296298
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration d’une stratégie Qualité de service pour vos serveurs Edge A/V

 

_**Dernière rubrique modifiée :** 2012-10-19_

Outre la création de stratégies QoS pour vos serveurs de conférence, d’applications et de médiation, vous devez également créer des stratégies audio et vidéo pour le côté interne de vos serveurs Edge A/V. Les stratégies utilisées dans vos serveurs Edge sont cependant différentes de celles utilisées dans vos serveurs de conférence, d’applications et de médiation. Pour ces derniers en effet, vous avez spécifié une plage de ports source, tandis qu’avec les serveurs Edge, vous devez indiquer une plage de ports de destination. C’est pour cette raison que vous ne pouvez pas simplement appliquer les stratégies QoS des serveurs de conférence, d’applications et de médiation à vos serveurs Edge  : ces stratégies ne fonctionneront tout simplement pas. Vous devez à la place créer de nouvelles stratégies pour les appliquer à vos serveurs Edge uniquement.

La procédure suivante explique comment créer des objets de stratégie de groupe Active Directory qui permettent de gérer la qualité de service (QoS) sur les serveurs Edge. Il est évidemment possible que vos serveurs Edge soient des serveurs autonomes non dotés de comptes Active Directory. Dans ce cas, vous pouvez utiliser la stratégie de groupe locale à la place de la stratégie de groupe Active Directory : la seule différence réside dans le fait que vous devez créer ces stratégies locales à l’aide de l’Éditeur d’objets de stratégie de groupe et que vous devez créer individuellement le même jeu de stratégies sur chaque serveur Edge. Pour démarrer l’Éditeur d’objets de stratégie de groupe sur un serveur Edge, procédez comme suit :

1.  Cliquez sur **Démarrer**, puis sur **Exécuter**.

2.  Dans la boîte de dialogue **Exécuter**, tapez **gpedit.msc**, puis appuyez sur ENTRÉE.

Si vous créez des stratégies Active Directory, vous devez ouvrir une session sur un utilisateur sur lequel la Gestion des stratégies de groupe est installée. Dans ce cas, ouvrez la Gestion des stratégies de groupe (cliquez sur **Démarrer**, pointez sur **Outils d’administration**, puis cliquez sur **Gestion des stratégies de groupe**), puis suivez les étapes ci-dessous :

1.  Dans la Gestion des stratégies de groupe, recherchez le conteneur dans lequel créer la nouvelle stratégie. Par exemple, si tous vos ordinateurs Lync Server se trouvent dans une unité d’organisation nommée Lync Server, la nouvelle stratégie doit être créée dans l’unité d’organisation Lync Server.

2.  Cliquez avec le bouton droit sur le conteneur approprié, puis cliquez sur **Créer un objet GPO dans ce domaine, et le lier ici**.

3.  Dans la boîte de dialogue **Nouvel objet GPO**, tapez le nom du nouvel objet de stratégie de groupe dans la zone **Nom** (par exemple, **Audio Lync Server**), puis cliquez sur **OK**.

4.  Cliquez avec le bouton droit sur la stratégie nouvellement créée, puis cliquez sur **Modifier**.

À partir de ce stade, le processus est ensuite identique pour créer une stratégie Active Directory ou une stratégie locale :

1.  Dans l’Éditeur de gestion des stratégies de groupe ou dans l’Éditeur d’objets de stratégie de groupe, développez **Configuration ordinateur**, **Stratégies**, **Paramètres Windows**, cliquez avec le bouton droit sur **QoS basée sur la stratégie**, puis cliquez sur **Créer une stratégie**.

2.  Dans la boîte de dialogue **QoS basée sur la stratégie**, dans la page d’accueil, tapez le nom de la nouvelle stratégie (par exemple, **Audio Lync Server**) dans la zone **Nom**. Sélectionnez **Spécifier la valeur DSCP** et indiquez la valeur **46**. Laissez la case à cocher **Spécifier le taux d’accélération en sortie** désactivée, puis cliquez sur **Suivant**.

3.  Dans la page suivante, assurez-vous que l’option **Toutes les applications** est sélectionnée, puis cliquez sur **Suivant**. Ce paramètre donne l’instruction au réseau de rechercher tous les paquets avec un marquage DSCP 46, et pas seulement les paquets créés par une application spécifique.

4.  Sur la troisième page, assurez-vous que les deux paramètres **Toute adresse IP source** et **Toute adresse IP de destination** sont sélectionnés, puis cliquez sur **Suivant**. Ces deux paramètres permettent de s’assurer que les paquets seront gérés, quel que soit l’ordinateur (adresse IP) qui a envoyé ces paquets et quel que soit l’ordinateur (adresse IP) qui les recevra.

5.  Page quatre, sélectionnez **TCP et UDP** dans la liste déroulante **Sélectionnez le protocole auquel s’applique cette stratégie de QoS**. TCP (Transmission Control Protocol) et UDP (User Datagram Protocol) sont les deux protocoles réseau les plus couramment utilisés par Lync Server et ses applications clientes.

6.  Sous l’en-tête **Spécifiez le numéro de port de destination**, sélectionnez **Vers ce numéro de port ou plage de destination**. Dans la zone de texte correspondante, tapez la plage de ports réservée aux transmissions audio. Par exemple, si vous avez réservé les ports 49152 à 57500 pour le trafic audio, entrez la plage de ports en suivant ce format : **49152:57500**. Cliquez sur **Terminer**.

Après avoir créé la stratégie QoS pour le trafic audio, vous devez créer une deuxième stratégie pour le trafic vidéo. Pour ce faire, suivez la même procédure de base que celle que vous avez suivie pour créer la stratégie audio, en effectuant les substitutions suivantes :

  - Utilisez un nom de stratégie différent et unique (par exemple, **Vidéo Lync Server**).

  - Attribuez à la valeur DSCP la valeur **34** au lieu de 46. (Notez que vous n’êtes pas obligé d’attribuer la valeur 34 à la valeur DSCP. Le seul impératif est d’utiliser une valeur DSCP pour la vidéo différente de celle utilisée pour l’audio).

  - Utilisez la plage de ports configurée précédemment pour le trafic vidéo. Par exemple, si vous avez réservé les ports 57501 à 65535 pour la vidéo, définissez la plage de ports comme ceci : **57501:65535**. Ceci doit être défini comme plage de ports de destination.

Si vous décidez de créer une stratégie pour gérer le trafic de partage d’application, vous devez créer une troisième stratégie en effectuant les substitutions suivantes :

  - Utilisez un nom de stratégie différent et unique (par exemple, **Partage d’application Lync Server**).

  - Attribuez à la valeur DSCP la valeur **24** au lieu de 46. (Là encore, vous n’êtes pas obligé d’attribuer la valeur 24 à la valeur DSCP. Le seul impératif est d’utiliser une valeur DSCP pour le partage d’application différente de celle utilisée pour l’audio ou la vidéo).

  - Utilisez la plage de ports configurée précédemment pour le trafic vidéo. Par exemple, si vous avez réservé les ports 40803 à 49151 pour le partage d’application, définissez la plage de ports comme ceci : **40803:49151**.

Les nouvelles stratégies que vous avez créées ne prendront effet que lorsque vous aurez actualisé la stratégie de groupe sur vos serveurs Edge. Même si la stratégie de groupe est automatiquement actualisée à intervalles réguliers, vous pouvez effectuer une actualisation immédiate en exécutant la commande suivante sur chaque ordinateur où la stratégie de groupe doit être actualisée :

    Gpudate.exe /force

Cette commande peut être exécutée dans Lync Server ou dans n’importe quelle fenêtre Commande qui s’exécute sous des informations d’identification d’administrateur. Pour ce faire, cliquez sur **Démarrer**, cliquez avec le bouton droit sur **Invite de commandes**, puis cliquez sur **Exécuter en tant qu’administrateur**. Notez que vous devrez peut-être redémarrer le serveur Edge même après l’exécution de Gpudate.exe.

Pour vous assurer que les paquets réseau sont bien marqués avec la valeur DSCP appropriée, vous devez également créer une entrée de Registre sur chaque ordinateur. Pour cela, procédez comme suit :

1.  Cliquez sur **Démarrer**, puis sur **Exécuter**.

2.  Dans la boîte de dialogue **Exécuter**, tapez **regedit**, puis appuyez sur Entrée.

3.  Dans l’Éditeur du Registre, développez successivement **HKEY\_LOCAL\_MACHINE**, **SYSTEM**, **CurrentControlSet**, **services**, puis **Tcpip**.

4.  Cliquez avec le bouton droit sur **Tcpip**, pointez sur **Nouveau**, puis cliquez sur **Clé**. Une fois la clé de Registre créée, tapez **QoS**, puis appuyez sur Entrée pour renommer la clé.

5.  Cliquez avec le bouton droit sur **QoS**, pointez sur **Nouveau**, puis cliquez sur **Valeur chaîne**. Une fois la clé de Registre créée, tapez **Ne pas utiliser NLA**, puis appuyez sur Entrée pour renommer la clé.

6.  Double-cliquez sur **Ne pas utiliser NLA**. Dans la boîte de dialogue **Modification de la chaîne**, tapez **1** dans la zone **Données de la valeur**, puis cliquez sur **OK**.

7.  Fermez l’Éditeur du Registre, puis redémarrez votre ordinateur.

