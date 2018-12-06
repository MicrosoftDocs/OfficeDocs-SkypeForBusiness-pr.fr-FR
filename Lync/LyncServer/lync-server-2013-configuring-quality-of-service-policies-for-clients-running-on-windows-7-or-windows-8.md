---
title: "Conf. des strat. de qual. de serv. pour clients exéc. sur Windows 7 ou 8"
TOCtitle: "Conf. des strat. de qual. de serv. pour clients exéc. sur Windows 7 ou 8"
ms:assetid: efff2b98-b3fb-4183-a4f0-329a9105ce2c
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205371(v=OCS.15)
ms:contentKeyID: 49299297
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des stratégies de qualité de service pour les clients exécutés sur Windows 7 ou Windows 8

 

_**Dernière rubrique modifiée :** 2016-03-29_

En plus de spécifier les plages de ports que vos clients Lync utiliseront, vous devez également séparer les stratégies de qualité de service qui seront appliquées aux ordinateurs clients. (Les stratégies de qualité de service créées pour les serveurs de conférence, d’application et de médiation ne doivent pas être appliquées aux ordinateurs clients.) Ces informations s’appliquent uniquement aux ordinateurs exécutant le client Lync 2013 et Windows 7 ou Windows 8.

L’exemple suivant utilise cet ensemble de plages de ports pour créer une stratégie audio et une stratégie vidéo :


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Type de trafic du client</th>
<th>Début du port</th>
<th>Plage de ports</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Audio</p></td>
<td><p>50020</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>Vidéo</p></td>
<td><p>58000</p></td>
<td><p>20</p></td>
</tr>
<tr class="odd">
<td><p>Partage d’application</p></td>
<td><p>42000</p></td>
<td><p>20</p></td>
</tr>
<tr class="even">
<td><p>Transfert de fichiers</p></td>
<td><p>42020</p></td>
<td><p>20</p></td>
</tr>
</tbody>
</table>


Pour créer une stratégie audio de qualité de service pour des ordinateurs Windows 7 ou Windows 8, commencez par vous connecter sur un ordinateur où la gestion des stratégies de groupe est installée. Ouvrez la Gestion des stratégies de groupe (cliquez sur **Démarrer**, pointez sur **Outils d’administration**, puis cliquez sur **Gestion des stratégies de groupe**) et procédez comme suit :

1.  Dans Gestion des stratégies de groupe, localisez le conteneur dans lequel créer la nouvelle stratégie. Par exemple, si tous vos ordinateurs clients sont situés dans une unité d’organisation (OU) nommée Clients, la nouvelle stratégie doit être créée dans l’OU cliente.

2.  Cliquez avec le bouton droit sur le conteneur approprié, puis cliquez sur **Créer un objet de stratégie de groupe dans ce domaine et le lier ici**.

3.  Dans la boîte de dialogue **Nouvel objet de stratégie de groupe** tapez un nom pour le nouvel objet de stratégie de groupe dans la zone **Nom** (par exemple, **Audio Lync**), puis cliquez sur **OK**.

4.  Cliquez avec le bouton droit sur la stratégie créée, puis cliquez sur **Modifier**.

5.  Dans l’Éditeur Gestion des stratégies de groupe, développez **Configuration de l’ordinateur**, puis **Stratégies** et **Paramètres Windows**. Cliquez avec le bouton droit sur **Qualité de service basée sur la stratégie**, puis cliquez sur **Créer une nouvelle stratégie**.

6.  Dans la boîte de dialogue **Qualité de service basée sur la stratégie**, sur la page d’ouverture, tapez un nom pour la nouvelle stratégie (par exemple, **Audio Lync**) dans la zone **Nom**. Sélectionnez **Spécifier une valeur DSCP** et définissez la valeur sur **46**. Laissez l’option **Spécifier le taux d’accélération en sortie** désactivée, puis cliquez sur **Suivant**.

7.  Sur la page suivante, vérifiez que l’option **Toutes les applications** est sélectionnée, puis cliquez sur **Suivant**. Ce paramètre indique au réseau de rechercher tous les paquets avec un marquage de 46, et non uniquement les paquets créés par une application spécifique.

8.  Sur la troisième page, vérifiez que les options **Toutes les adresses IP sources** et **Toutes les adresses IP de destination** sont sélectionnées, puis cliquez sur **Suivant**. Ces deux paramètres permettent de s’assurer que les paquets seront gérés quels que soient l’ordinateur (adresse IP) qui les a envoyés et celui qui les reçoit.

9.  Sur la quatrième page, sélectionnez **TCP et UDP** dans la liste déroulante **Sélectionnez le protocole auquel s’applique cette stratégie de qualité de service**. TCP (Transmission Control Protocol) et UDP (User Datagram Protocol) sont les deux protocoles de gestion de réseau les plus utilisés par Lync Server et ses applications clientes.

10. Sous le titre **Spécifiez le numéro de port source**, sélectionnez **À partir de ce port ou de cette plage source**. Dans la zone de texte associée, tapez la plage de ports réservée aux transmissions audio. Par exemple, si vous avez réservé les ports 50020 à 50039 pour le trafic audio, entrez la plage de ports en utilisant ce format : **50020:50039**. Cliquez sur **Terminer**.

Après avoir créé la stratégie de qualité de service pour l’audio, vous devez créer une deuxième stratégie pour la vidéo. Pour créer une stratégie vidéo, respectez la même procédure de base que pour la création de la stratégie audio, en effectuant les remplacements suivants :

  - utilisez un nom de stratégie différent et unique (par exemple, **Vidéo Lync**) ;

  - définissez la valeur DSCP sur **34** au lieu de 46. (Comme indiqué précédemment, vous n’êtes pas obligé d’utiliser la valeur DSCP 34 ; vous devez simplement attribuer une valeur DSCP différente de celle utilisée pour l’audio.) ;

  - utilisez la plage de ports configurée précédemment pour le trafic vidéo. Par exemple, si vous avez réservé les ports 58000 à 58019 pour la vidéo, définissez la plage de ports sur : **58000:58019**.

Si vous décidez de créer une stratégie pour gérer le trafic du partage d’application, effectuez les remplacements suivants :

  - utilisez un nom de stratégie différent et unique (par exemple, **Partage d’application Lync Server**) ;

  - définissez la valeur DSCP sur **24** au lieu de 46. (Encore une fois, cette valeur ne doit pas forcément être 24 ; elle doit simplement être différente des valeurs DSCP utilisées pour l’audio et la vidéo.) ;

  - utilisez la plage de ports configurée précédemment pour le trafic vidéo. Par exemple, si vous avez réservé les ports 42000 à 42019 pour le partage d’application, définissez la plage de ports sur : **42000:42019**.

Pour une stratégie de transfert de fichiers :

  - utilisez un nom de stratégie différent et unique (par exemple, **Transfert de fichiers Lync Server**) ;

  - définissez la valeur DSCP sur **14**. (Encore une fois, cette valeur ne doit pas forcément être 14 ; elle doit simplement constituer un code DSCP unique.) ;

  - utilisez la plage de ports configurée précédemment pour le partage d’application. Par exemple, si vous avez réservé les ports 42020 à 42039 pour le partage d’application, définissez la plage de ports sur : **42020:42039**.

Les nouvelles stratégies créées ne prennent effet qu؊’une fois que la stratégie de groupe a été actualisée sur vos ordinateurs clients. Même si la stratégie de groupe s’actualise régulièrement, vous pouvez forcer une actualisation immédiate en exécutant la commande suivante sur chaque ordinateur où la stratégie de groupe doit être actualisée :

    Gpudate.exe /force

Cette commande peut être exécutée à partir de n’importe quelle fenêtre de commande exécutée avec des informations d’identification d’administrateur. Pour exécuter une fenêtre de commande avec des informations d’identification d’administrateur, cliquez sur **Démarrer**, cliquez avec le bouton droit sur **Invite de commande**, puis cliquez sur **Exécuter en tant qu’administrateur**.

Rappelez-vous que ces stratégies doivent cibler des ordinateurs clients. Elles ne doivent pas être appliquées aux serveurs exécutant Lync Server.

Afin de vous assurer que les paquets réseau sont marqués avec la valeur DSCP appropriée, vous devez également créer une nouvelle entrée de registre sur chaque ordinateur en procédant comme suit :

1.  Cliquez sur **Démarrer**, puis **Exécuter**.

2.  Dans la boîte de dialogue **Exécuter**, tapez **regedit** et appuyez sur Entrée.

3.  Dans l’Éditeur du Registre, développez **HKEY\_LOCAL\_MACHINE**, **SYSTEM**, **CurrentControlSet**, **services**, puis **Tcpip**.

4.  Cliquez avec le bouton droit sur **Tcpip**, pointez sur **Nouveau**, puis cliquez sur **Clé**. Une fois la nouvelle clé de registre créée, tapez **QoS** et appuyez sur Entrée pour renommer la clé.

5.  Cliquez avec le bouton droit sur **QoS**, pointez sur **Nouveau**, puis cliquez sur **Valeur de chaîne**. Une fois la nouvelle valeur de registre créée, tapez **Ne pas utiliser NLA** et appuyez sur Entrée pour renommer la valeur.

6.  Double-cliquez sur **Ne pas utiliser NLA**. Dans la boîte de dialogue **Modifier la chaîne**, tapez **1** dans la zone **Données de valeur**, puis cliquez sur **OK**.

7.  Fermez l’Éditeur du Registre et redémarrez votre ordinateur.

## Configuration de la qualité de service sur les ordinateurs ayant plusieurs cartes réseau

Si votre ordinateur possède plusieurs cartes réseau, il se pourrait que vous rencontriez des problèmes, où la valeur 0x00 est indiquée au lieu de la valeur DSCP configurée. Cela se produit généralement sur les ordinateurs où une ou plusieurs cartes réseau ne peuvent pas accéder à votre domaine Active Directory (par exemple, si ces cartes sont utilisées pour un réseau privé). Dans ces cas, les valeurs DSCP sont balisées pour les cartes qui peuvent accéder au domaine, mais ne sont pas balisées pour les cartes qui ne peuvent pas y accéder.

Si vous voulez baliser les valeurs DSCP pour toutes les cartes réseau d’un ordinateur, y compris les cartes qui n’ont pas accès à votre domaine, vous devez ajouter et configurer une valeur au registre. Pour cela, effectuez la procédure suivante :

1.  Cliquez sur **Démarrer**, puis **Exécuter**.

2.  Dans la boîte de dialogue **Exécuter**, tapez **regedit** et appuyez sur Entrée.

3.  Dans l’Éditeur du Registre, développez **HKEY\_LOCAL\_MACHINE**, **SYSTEM**, **CurrentControlSet**, **services**, puis **Tcpip**.

4.  Si vous ne voyez pas de clé de registre **QoS**, cliquez avec le bouton droit sur **Tcpip**, pointez sur **Nouveau**, puis cliquez sur **Clé**. Une fois la nouvelle clé créée, tapez **QoS**, puis appuyez sur Entrée pour renommer la clé.

5.  Cliquez avec le bouton droit sur **QoS**, pointez sur **Nouveau**, puis cliquez sur **Valeur de chaîne**. Une fois la nouvelle valeur de registre créée, tapez **Ne pas utiliser NLA** et appuyez sur Entrée pour renommer la valeur.

6.  Double-cliquez sur **Ne pas utiliser NLA**. Dans la boîte de dialogue **Modifier la chaîne**, tapez **1** dans la zone **Données de valeur**, puis cliquez sur **OK**.

Une fois la nouvelle valeur de registre créée et configurée, vous devez redémarrer votre ordinateur pour que les modifications prennent effet.

