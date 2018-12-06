---
title: "LS 2013 : Conf. strat. de qual. de service pr serv. de conf, d’app. et de méd."
TOCTitle: Configuration d’une stratégie de qualité de service pour les serveurs de conférence, d’application et de médiation
ms:assetid: 8adcbbc5-c9f5-476d-ab7f-72e61859cacf
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205076(v=OCS.15)
ms:contentKeyID: 49298009
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration d’une stratégie de qualité de service dans Lync Server 2013 pour les serveurs de conférence, d’application et de médiation

 

_**Dernière rubrique modifiée :** 2014-06-23_

La configuration de plages de ports facilite l’utilisation de la qualité de service en s’assurant que tout le trafic d’un type donné (par exemple, tout le trafic audio) passe par le même ensemble de ports. Cela permet au système d’identifier et de marquer facilement un paquet donné : si le port 49152 est réservé au trafic audio, les paquets qui passent par le port 49152 peuvent être marqués avec un code DSCP qui indique qu’il s’agit d’un paquet audio. Cela permet aux routeurs d’identifier le paquet comme étant un paquet audio, et de lui donner une priorité supérieure aux paquets non marqués (par exemple, les paquets utilisés pour copier un fichier d’un serveur sur un autre).

Cependant, la limitation d’un ensemble de ports à un type de trafic spécifique ne permet pas que ces paquets soient automatiquement marqués avec le code DSCP approprié. En plus de la définition des plages de ports, vous devez également créer des stratégies de qualité de service qui spécifient le code DSCP à associer à chaque plage de ports. Pour Microsoft Lync Server 2013 cela signifie la création de deux stratégies : une pour l’audio et l’autre pour la vidéo.

Il est facile de créer et de gérer des stratégies de qualité de service avec la Stratégie de groupe. (Ces stratégies peuvent également être créées à l’aide de stratégies de sécurité locales. Cependant, cela nécessite de répéter la même procédure sur chaque ordinateur.) Votre ensemble initial de stratégies QoS (une pour l’audio et l’autre pour la vidéo) doit être appliqué uniquement aux ordinateurs Lync Server qui exécutent les services de serveur de conférence, serveur d’applications et/ou serveur de médiation. Si tous ces ordinateurs sont situés dans la même unité d’organisation Active Directory, il suffit d’affecter le nouvel objet de stratégie de groupe (GPO) à cette unité d’organisation. Vous pouvez également procéder d’une autre façon pour cibler les ordinateurs spécifiés avec cette stratégie ; par exemple, vous pouvez placer les ordinateurs dans un groupe de sécurité, puis utiliser le filtrage de sécurité de la stratégie de groupe pour appliquer l’objet de stratégie de groupe uniquement à ce groupe de sécurité.

Pour créer une stratégie de qualité de service pour gérer l’audio, connectez-vous à un ordinateur sur lequel la gestion des stratégies de groupe est installée. Ouvrez la gestion des stratégies de groupe (cliquez sur **Démarrer** , pointez sur **Outils d’administration** , puis cliquez sur **Gestion des stratégies de groupe** ) et effectuez la procédure suivante :

1.  Dans la gestion des stratégies de groupe, accédez au conteneur dans lequel la nouvelle stratégie doit être créée. Par exemple, si tous vos ordinateurs Lync Server sont situés dans une unité d’organisation appelée Lync Server, la nouvelle stratégie doit être créée dans l’unité d’organisation Lync Server.

2.  Cliquez avec le bouton droit sur le conteneur approprié, puis cliquez sur **Créer un objet GPO dans ce domaine, et le lier ici** .

3.  Dans la boîte de dialogue **Nouvel objet GPO** , saisissez le nom du nouvel objet de stratégie de groupe dans la zone **Nom** (par exemple, **Qos Lync Server** ), puis cliquez sur **OK** .

4.  Cliquez avec le bouton droit sur la stratégie nouvellement créée, puis cliquez sur **Modifier** .

5.  Dans l’Éditeur de gestion des stratégies de groupe, développez **Configuration ordinateur** , **Stratégies** , **Paramètres Windows** , cliquez avec le bouton droit sur **QoS basée sur la stratégie** , puis cliquez sur **Créer une nouvelle stratégie** .

6.  Dans la boîte de dialogue **QoS basée sur la stratégie** , dans la page d’accueil, tapez le nom de la nouvelle stratégie (par exemple, **Qos Lync Server** ) dans la zone **Nom** . Sélectionnez **Spécifier la valeur DSCP** et indiquez la valeur  **46** . Laissez la case **Spécifier le taux d’accélération en sortie** décochée, puis cliquez sur **Suivant** .

7.  Dans la page suivante, assurez-vous que **Toutes les applications** est sélectionné, puis cliquez sur **Suivant** . Cela permet de s’assurer que toutes les applications feront correspondre les paquets de la plage de ports spécifiée au code DSCP correct.

8.  Dans la troisième page, vérifiez que **Toute adresse IP source et Toute adresse IP de destination** sont sélectionnés, puis cliquez sur **Suivant** . Ces deux paramètres permettent que tous les paquets soient gérés quel que soit l’ordinateur (adresse IP) qui a envoyé ces paquets et l’ordinateur (adresse IP) qui les reçoit.

9.  Page quatre, sélectionnez **TCP et UDP** dans la liste déroulante **Sélectionnez le protocole auquel s’applique cette stratégie de QoS** . TCP (Transmission Control Protocol) et UDP (User Datagram Protocol) sont les deux protocoles réseau les plus couramment utilisés par Lync Server et ses applications clientes.

10. Sous le titre **Spécifiez le numéro de port source** , sélectionnez **À partir de ce port ou plage source** . Dans la zone de texte correspondante, tapez la plage de ports réservée pour les transmissions audio. Par exemple, si vous réservez les ports 49152 à 57500 pour le trafic audio, tapez la plage de ports au format : **49152:57500** . Cliquez sur **Terminer** .

> [!NOTE]  
> La valeur DSCP 46 est arbitraire : même si DSCP 46 est souvent utilisé pour marquer les paquets audio, vous n’êtes pas obligé d’utiliser cette valeur pour les communications audio. Si vous avez déjà mis en œuvre QoS et utilisez un autre code DSCP pour l’audio (par exemple, DSCP 40), configurez votre stratégie de qualité de service pour qu’elle utilise ce code (c’est-à-dire, 40 pour l’audio). Si vous implémentez la qualité de service, alors il est recommandé d’utiliser DSCP 46 pour l’audio, car cette valeur est utilisée en général pour marquer les paquets audio.

Une fois la stratégie QoS créée pour le trafic audio, créez une seconde stratégie pour le trafic vidéo (et une troisième pour la gestion du trafic de partage d’applications, si vous le souhaitez). Pour créer une stratégie pour la vidéo, suivez la procédure indiquée pour l’audio, et remplacez les éléments suivants :

  - Utilisez un nom de stratégie différent et unique (par exemple, **Vidéo Lync Server** ).

  - Attribuez à la valeur DSCP la valeur  **34** au lieu de 46. (Notez que vous n’êtes pas obligé d’attribuer la valeur 34 à la valeur DSCP. Le seul impératif est d’utiliser une valeur DSCP pour la vidéo différente de celle utilisée pour l’audio).

  - Utilisez la plage de ports configurée précédemment pour le trafic vidéo. Par exemple, si vous avez réservé les ports 57501 à 65535 pour la vidéo, définissez la plage de ports comme ceci : **57501:65535** .

Si vous décidez de créer une stratégie de gestion du trafic de partage d’application, vous devez créer une troisième stratégie en effectuant les substitutions suivantes :

  - Utilisez un nom de stratégie différent et unique (par exemple, **Partage d’application Lync Server** ).

  - Attribuez à la valeur DSCP la valeur  **24** au lieu de 46. (Là encore, vous n’êtes pas obligé d’attribuer la valeur 24 à la valeur DSCP. Le seul impératif est d’utiliser une valeur DSCP pour le partage d’application différente de celle utilisée pour l’audio ou la vidéo).

  - Utilisez la plage de ports configurée précédemment pour le trafic vidéo. Par exemple, si vous avez réservé les ports 40803 à 49151 pour le partage d’application, définissez la plage de ports comme ceci : **40803:49151** .

Les nouvelles stratégies que vous avez crées ne sont pas appliquées tant que vous n’avez pas actualisé la stratégie de groupe sur vos ordinateurs Lync Server. Même si la stratégie de groupe s’actualise périodiquement, vous pouvez forcer une actualisation immédiate en utilisant la commande suivante sur les ordinateurs sur lesquels la stratégie de groupe doit être actualisée :

    Gpupdate.exe /force

Cette commande peut être exécutée dans Lync Server Management Shell ou à partir d’une fenêtre de commande avec des informations d’identification d’administrateur. Pour exécuter une fenêtre de commande avec des droits d’administrateur, cliquez sur **Démarrer** , cliquez avec le bouton droit sur **Invite de commandes** , puis cliquez sur **Exécuter en tant qu’administrateur** .

Pour vérifier que les nouvelles stratégies QoS ont été appliquées, procédez ainsi :

1.  Sur l’ordinateur Lync Server, cliquez sur **Démarrer** , puis sur **Exécuter** .

2.  Dans la boîte de dialogue **Exécuter** , tapez **regedit** , puis appuyez sur Entrée.

3.  Dans l’Éditeur du Registre, développez successivement **Ordinateur** , **HKEY\_LOCAL\_MACHINE** , **SOFTWARE** , **Stratégies** , **Microsoft** , **Windows** , puis cliquez sur **QoS** . Sous **QoS** , des clés de Registre pour chaque stratégie QoS créée doivent s’afficher. Par exemple, si vous avez créé deux stratégies (une nommée Qos Audio Lync Server et l’autre Qos Vidéo Lync Server), vous devez voir ces deux stratégies dans le Registre.

Pour vous assurer que les paquets réseau sont bien marqués avec la valeur DSCP appropriée, vous devez également créer une entrée de Registre sur chaque ordinateur. Pour cela, procédez comme suit :

1.  Pour ce faire, cliquez sur **Démarrer** , puis sur **Exécuter** .

2.  Dans la boîte de dialogue **Exécuter** , tapez **regedit** , puis appuyez sur Entrée.

3.  Dans l’Éditeur du Registre, développez successivement **HKEY\_LOCAL\_MACHINE** , **SYSTEM** , **CurrentControlSet** , **services** , puis **Tcpip** .

4.  Cliquez avec le bouton droit sur **Tcpip** , pointez sur **Nouveau** , puis cliquez sur **Clé** . Une fois la clé de Registre créée, tapez **QoS** , puis appuyez sur Entrée pour renommer la clé.

5.  Cliquez avec le bouton droit sur **QoS** , pointez sur **Nouveau** , puis cliquez sur **Valeur chaîne** . Une fois la clé de Registre créée, tapez **Ne pas utiliser NLA** , puis appuyez sur Entrée pour renommer la clé.

6.  Double-cliquez sur **Ne pas utiliser NLA** . Dans la boîte de dialogue **Modification de la chaîne** , saisissez  **1** dans la zone **Données de la valeur** , puis cliquez sur **OK** .

7.  Fermez l’Éditeur du Registre, puis redémarrez votre ordinateur.

