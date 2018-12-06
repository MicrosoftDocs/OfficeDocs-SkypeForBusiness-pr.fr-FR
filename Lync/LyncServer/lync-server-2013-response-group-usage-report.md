---
title: 'Lync Server 2013 : Rapport d’utilisation de Response Group'
TOCTitle: Rapport d’utilisation de Response Group
ms:assetid: 3248b320-a552-400a-8485-6891af4eb0f3
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg558632(v=OCS.15)
ms:contentKeyID: 49296795
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Rapport d’utilisation de Response Group dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

L’application Response Group permet à Microsoft Lync Server 2013 de répondre et d’acheminer des appels téléphoniques en fonction du numéro qui a été composé et, éventuellement, d’un ensemble de réponses à des questions posées à l’appelant. En règle générale, les appels Response Group ne sont pas acheminés vers une personne, mais vers un ensemble de personnes connu sous le nom de groupe d’agents. Par exemple, si une personne appelle le numéro de téléphone de votre support technique, Lync Server 2013 peut automatiquement acheminer l’appel vers le premier agent disponible du support technique. Lync Server peut aussi poser un ensemble de questions (« Appuyez sur 1 si vous avez des problèmes matériel. Appuyez sur 2 pour des problèmes logiciels. Appuyez sur 3 pour des problèmes réseau. ») puis acheminer l’appel vers l’agent du support technique le plus à même de résoudre le problème en fonction des réponses données.

Le rapport d’utilisation de Response Group donne une vision détaillée du nombre d’appels téléphoniques reçus par tous vos flux de travail Response Group, puis répartit ces appels en catégories plus précises telles que Appels offerts, Appels ayant obtenu une réponse et Appels abandonnés.

La meilleure façon de tirer parti du rapport d’utilisation de Response Group est de comprendre la différence entre les types d’appel signalés :

  - **Appels reçus**. Nombre total d’appels reçus par toutes les instances de l’application Response Group.

  - **Appels réussis**. Nombre d’appels reçus par l’application Response Group.

  - **Appels offerts**. Nombre total d’appels transférés à un agent Response Group.

  - **Appels ayant obtenu une réponse**. Nombre total d’appels auxquels un agent Response Group a effectivement répondu.

  - **Pourcentage d’appels abandonnés**  : pourcentage d’appels reçus par l’application Response Group mais n’ayant reçu aucune réponse de la part d’un agent. Cette valeur est calculée en soustrayant les appels avec réponse des appels reçus, puis en divisant cette valeur par le nombre d’appels reçus. Par exemple, si vous recevez 10 appels dont 7 avec réponse, vous retranchez 7 de 10 et obtenez donc 3 appels sans réponse. Divisez ensuite cette valeur par 10, ce qui vous donne un pourcentage d’appels abandonnés de 30 %.

  - **Appels transférés**. Nombre total d’appels Response Group ayant été transférés pour cause d’expiration ou de débordement de la file d’attente.

Si vous examinez le rapport d’utilisation de Response Group et que vous ne vous souvenez pas de la définition des types d’appels indiqués, il suffit de pointer le curseur de la souris sur l’étiquette du type d’appel concerné et une info-bulle s’affiche contenant une brève description du type de l’appel.

Le rapport d’utilisation de Response Group vous permet de filtrer sur un URI de flux de travail (l’adresse SIP associée à ce flux de travail). Cependant, les URI de flux de travail ne s’affichent pas réellement dans le rapport. Si vous cherchez à identifier les flux de travail qui répondent le plus aux appels ou ceux qui reçoivent le plus d’appels transférés, cliquez sur la mesure appropriée pour ouvrir le rapport des listes d’appels Response Group pour la période donnée. Ce rapport, en revanche, indique les URI de flux de travail.

## Accéder au rapport d’utilisation de Response Group

Le rapport d’utilisation de Response Group est accessible depuis la page d’accueil Rapports de surveillance. Vous pouvez explorer le [Rapport de liste des appels Response Group dans Lync Server 2013](lync-server-2013-response-group-call-list-report.md) en cliquant sur l’une des mesures suivantes :

  - Appels reçus

  - Appels réussis

  - Appels offerts

  - Appels ayant obtenu une réponse

  - Appels transférés

## Tirer le meilleur parti du rapport d’utilisation de Response Group

L’utilisation la plus intéressante de ce rapport n’est peut-être pas la plus évidente : il s’agit de sa capacité à recueillir des informations d’utilisation pour un seul flux de travail Response Group.

> [!WARNING]  
> Un flux de travail Response Group est généralement un ensemble d’instructions qui détermine le comportement de Lync Server quand un utilisateur compose un numéro de téléphone spécifique. Dans cet objectif, chaque flux de travail est associé de manière unique à un numéro de téléphone. Quand une personne appelle ce numéro, le flux de travail détermine la façon dont l’appel sera géré. Par exemple, le flux de travail peut éventuellement faire en sorte que l’appel soit acheminé vers une série de questions du système de réponse vocale interactive qui invite l’utilisateur à entrer des informations supplémentaires (« Appuyez sur 1 pour accéder au support matériel. Appuyez sur 2 pour accéder au support logiciel. »). Le flux de travail peut aussi faire en sorte que l’appel soit placé dans une file d’attente, l’appelant est alors mis en attente jusqu’à ce qu’un agent puisse répondre à l’appel. La disponibilité des agents pour répondre aux appels est également déterminée par le flux de travail : les flux de travail servent à configurer les heures ouvrées (les jours de la semaine et les heures de la journée pendant lesquels les agents sont disponibles pour répondre aux appels) et les congés (les jours pendant lesquels les agents ne sont pas disponibles pour répondre aux appels). Chaque fois que vous composez un numéro de téléphone appartenant à l’application Response Group, vous appelez avant tout un flux de travail Response Group.

Même si les URI de flux de travail ne s’affichent pas dans le rapport d’utilisation de Response Group, il est encore possible d’afficher les statistiques d’utilisation pour un seul flux de travail, ce qui est souvent très utile. Par exemple, supposons que vous avez récemment lancé une nouvelle campagne publicitaire et que vous souhaitez savoir si des personnes appellent pour en savoir plus sur le produit. Si vous avez associé un flux de travail Response Group au numéro de téléphone indiqué dans la campagne publicitaire, vous pouvez facilement consulter le nombre de personnes (s’il y en a) qui ont appelé ce numéro.

Vous pouvez aussi utiliser une approche similaire pour évaluer le nombre d’appels gérés par votre support technique interne ou votre service client.

Pour consulter les statistiques d’utilisation d’un flux de travail en particulier, entrez l’URI du flux de travail dans la zone correspondante. Comme indiqué auparavant, les URI de flux de travail (adresse SIP associée au flux de travail) ne s’affichent pas dans le rapport. Cela signifie que vous devez utiliser un autre moyen pour déterminer l’URI d’un flux de travail. Vous pouvez notamment utiliser Windows PowerShell et Lync Server Management Shell. Par exemple, cette commande renvoie les URI de tous vos flux de travail Response Group :

    Get-CsRgsWorkflow | Select-Object Name, PrimaryUri

Des données semblables à ceci sont renvoyées :

    Name                            PrimaryUri
    ----                            ----------
    Customer Support                sip:support@litwareinc.com
    Help Desk                       sip:helpdesk@litwareinc.com
    New Ad Campaign                 sip:newads@litwareinc.com

Cette commande renvoie les informations relatives à un seul flux de travail, celui qui porte le nom « New Ad Campaign » :

    Get-CsRgsWorkflow -Name "New Ad Campaign" | Select-Object Name, PrimaryUri

## Filtres

Les filtres vous offrent la possibilité de renvoyer un ensemble de données mieux ciblées ou de visualiser les données renvoyées de différentes manières. Par exemple, le rapport d’utilisation de Response Group vous permet d’afficher les données de tous vos flux de travail Response Group ou d’un seul. Vous pouvez également choisir le mode de groupement des données. Dans ce cas, les utilisations sont groupées par heure, jour, semaine ou mois.

Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport d’utilisation de Response Group.

### Filtres du rapport d’utilisation de Response Group

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Nom</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>De</strong></p></td>
<td><p>Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :</p>
<p>7/7/2012 1:00 PM</p>
<p>Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</p>
<p>07/07/2012</p>
<p>Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</p>
<p>7/3/2012</p>
<p>Les semaines s’étalent toujours du dimanche au samedi.</p></td>
</tr>
<tr class="even">
<td><p><strong>À</strong></p></td>
<td><p>Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :</p>
<p>7/7/2012 1:00 PM</p>
<p>Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</p>
<p>07/07/2012</p>
<p>Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</p>
<p>7/3/2012</p>
<p>Les semaines s’étalent toujours du dimanche au samedi.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Intervalle</strong></p></td>
<td><p>Intervalle de temps. Sélectionnez l’une des options suivantes :</p><ul><li><p>Toutes les heures (il est possible d’afficher un maximum de 25 heures)</p></li><li><p>Tous les jours (il est possible d’afficher un maximum de 31 jours)</p></li><li><p>Toutes les semaines (il est possible d’afficher un maximum de 12 semaines)</p></li><li><p>Tous les mois (il est possible d’afficher un maximum de 12 mois)</p></li></ul>
<p>Si la période comprise entre les dates de début et de fin dépasse le nombre maximal de valeurs autorisé pour l’intervalle sélectionné, seul le nombre maximal de valeurs (à compter de la date de début) s’affiche. Par exemple, si vous sélectionnez l’intervalle Tous les jours avec une date de début le 7/7/2012 et une date de fin le 2/28/2012, les données s’affichent pour les jours compris entre le 8/7/2012 12:00 AM et le 9/7/2012 12:00 AM (c’est-à-dire, un total de 31 jours de données).</p></td>
</tr>
<tr class="even">
<td><p><strong>URI du flux de travail</strong></p></td>
<td><p>Vous permet de limiter les données renvoyées au flux de travail Response Group spécifié. Pour utiliser ce filtre, entrez l’adresse SIP du flux de travail. Par exemple :</p>
<p>sip:helpdesk@litwareinc.com</p></td>
</tr>
</tbody>
</table>


## Mesures

Le tableau qui suit répertorie les informations fournies dans le rapport d’utilisation de Response Group.

### Mesures du rapport d’utilisation de Response Group

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nom</th>
<th>Est-il possible d’effectuer un tri sur cet élément ?</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Toutes les heures</strong></p>
<p><strong>Tous les jours</strong></p>
<p><strong>Toutes les semaines</strong></p>
<p><strong>Tous les mois</strong></p></td>
<td><p>Non</p></td>
<td><p>Indique l’intervalle de temps sélectionné. Le cas échéant, vous pouvez cliquer sur un intervalle de temps donné pour afficher des informations détaillées pour cet intervalle. Par exemple, si vous utilisez l’intervalle Tous les jours et que vous cliquez sur 7/7/2012, une répartition par jour de l’activité d’enregistrement utilisateur est affichée pour cette date.</p></td>
</tr>
<tr class="even">
<td><p><strong>Appels reçus</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total d’appels reçus par toutes les instances de l’application Response Group. Lorsque vous cliquez sur cet élément, le rapport vous montre le rapport des listes d’appels Response Group correspondant à la période sélectionnée.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Appels réussis</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total d’appels auxquels l’application Response Group a répondu. Lorsque vous cliquez sur cet élément, le rapport vous montre le rapport des listes d’appels Response Group correspondant à la période sélectionnée.</p></td>
</tr>
<tr class="even">
<td><p><strong>Appels offerts</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total d’appels qui ont été transférés à un agent Response Group. Lorsque vous cliquez sur cet élément, le rapport vous montre le rapport des listes d’appels Response Group correspondant à la période sélectionnée.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Appels ayant obtenu une réponse</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total d’appels auxquels un agent Response Group a effectivement répondu. Lorsque vous cliquez sur cet élément, le rapport vous montre le rapport des listes d’appels Response Group correspondant à la période sélectionnée.</p></td>
</tr>
<tr class="even">
<td><p><strong>Pourcentage d’appels abandonnés</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total d’appels reçus par l’application Response Group mais n’ayant reçu aucune réponse de la part d’un agent. Ce chiffre est calculé en soustrayant les appels avec réponse des appels reçus, puis en divisant cette valeur par le nombre d’appels reçus. Par exemple, si vous avez 10 appels reçus et sept avec réponse, vous soustrayez sept de 10 et obtenez donc trois appels sans réponse. Divisez ensuite cette valeur par 10, ce qui vous fournit un pourcentage d’appels abandonnés de 30%.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Minutes d’appel moyennes par agent</strong></p></td>
<td><p>Non</p></td>
<td><p>Temps moyen consacré par un agent Response Group à un appel.</p></td>
</tr>
<tr class="even">
<td><p><strong>Appels transférés</strong></p></td>
<td><p>Non</p></td>
<td><p>Nombre total d’appels Response Group ayant été transférés pour cause d’expiration ou de saturation de la file d’attente. Lorsque vous cliquez sur cet élément, le rapport vous montre le rapport des listes d’appels Response Group correspondant à la période sélectionnée.</p></td>
</tr>
</tbody>
</table>

