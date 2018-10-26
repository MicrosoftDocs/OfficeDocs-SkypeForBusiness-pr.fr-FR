---
title: 'Lync Server 2013 : Rapport de liste des appels Response Group'
TOCTitle: Rapport de liste des appels Response Group
ms:assetid: a2d3e08b-511b-4507-abba-8ff71aa27c8e
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg615443(v=OCS.15)
ms:contentKeyID: 49298376
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Rapport de liste des appels Response Group dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

L’application Response Group permet à Microsoft Lync Server 2013 de répondre et d’acheminer des appels téléphoniques en fonction du numéro qui a été composé et, éventuellement, d’un ensemble de réponses à des questions posées à l’appelant. En règle générale, les appels Response Group ne sont pas acheminés vers une personne, mais vers un ensemble de personnes connu sous le nom de groupe d’agents. Par exemple, si une personne appelle le numéro de téléphone de votre support technique, Lync Server 2013 peut automatiquement acheminer l’appel vers le premier agent disponible du support technique. Lync Server peut aussi poser un ensemble de questions (« Appuyez sur 1 si vous avez des problèmes matériel. Appuyez sur 2 pour des problèmes logiciels. Appuyez sur 3 pour des problèmes réseau. ») puis acheminer l’appel vers l’agent du support technique le plus à même de résoudre le problème en fonction des réponses données.

Le Rapport des listes d’appels Response Group représente une collection d’appels effectués pendant une période spécifiée et pour un type d’appel spécifié. Le Rapport d’utilisation de Response Group (qui doit être ouvert au préalable pour que vous puissiez ouvrir le Rapport des listes d’appels Response Group) reconnaît les types d’appels suivants :

  - **Appels reçus** . Nombre total d’appels reçus par toutes les instances de l’application Response Group.

  - **Appels réussis**.Nombre total d’appels auxquels l’application Response Group a répondu.

  - **Appels offerts** . Nombre total d’appels transférés à un agent Response Group.

  - **Appels ayant obtenu une réponse** . Nombre total d’appels auxquels un agent Response Group a effectivement répondu.

  - Pourcentage d’appels abandonnés. Pourcentage d’appels reçus par l’application Response Group mais n’ayant reçu aucune réponse de la part d’un agent. Cette valeur est calculée en soustrayant les appels avec réponse des appels reçus, puis en divisant cette valeur par le nombre d’appels reçus. Par exemple, si vous avez reçu dix appels et sept avec réponse, vous soustrayez sept de dix et obtenez donc trois appels sans réponse. Divisez ensuite cette valeur par dix, ce qui vous fournit un pourcentage d’appels abandonnés de 30 %.

  - **Appels transférés** . Nombre total d’appels Response Group ayant été transférés pour cause d’expiration ou de débordement de la file d’attente.

## Accès au Rapport des listes d’appels Response Group

Le Rapport des listes d’appels Response Group est accessible uniquement en cliquant sur l’une des mesures suivantes disponibles dans le [Rapport d’utilisation de Response Group dans Lync Server 2013](lync-server-2013-response-group-usage-report.md) :

  - Appels reçus

  - Appels réussis

  - Appels offerts

  - Appels ayant obtenu une réponse

  - Appels transférés

## Utilisation optimale du Rapport des listes d’appels Response Group

Le Rapport des listes d’appels Response Group vous permet de limiter les données affichées aux appels impliquant un flux de travail Response Group particulier. Pour cela, vous devez entrer l’URI de flux de travail (l’adresse SIP du flux de travail) dans la zone URI du flux de travail. Avant cela, vous devez cependant être en mesure de voir cette zone URI du flux de travail. Pour afficher les options de filtrage du Rapport des listes d’appels Response Group, cliquez sur le bouton Afficher / Masquer les paramètres dans la partie supérieure gauche de la fenêtre de rapport.

Notez que le Rapport des listes d’appels Response Group n’affiche pas d’informations relatives au code de réponse ou à l’ID de diagnostic si vous maintenez le pointeur de la souris sur l’une de ces mesures. Si vous souhaitez obtenir davantage d’informations, vous pouvez noter le code de réponse et/ou l’ID de diagnostic, puis rechercher ces valeurs dans le [Rapport des principales défaillances dans Lync Server 2013](lync-server-2013-top-failures-report.md).

Si vous souhaitez obtenir la réponse à une question telle que « Quel est le flux de travail ayant reçu le plus d’appels ? », vous pouvez procéder comme suit :

1.  Dans le Rapport d’utilisation de Response Group, définissez la période souhaitée, puis cliquez sur la mesure Appels reçus pour ouvrir le Rapport des listes d’appels Response Group.

2.  Exportez les données affichées dans le Rapport des listes d’appels Response Group. Par exemple, vous pourriez exporter les données au format Microsoft Excel, puis utiliser Excel pour convertir ces données en un fichier de valeurs séparées par des virgules.

3.  Exécutez vos analyses à l’aide de Windows PowerShell.

Par exemple, si vous avez enregistré les données dans un fichier nommé C:\\Data\\Response\_Group\_Call\_List\_Report.csv, vous pouvez utiliser la commande suivante pour renvoyer le nombre total d’appels reçus pour chaque flux de travail mentionné dans le rapport :

    $calls = Import-Csv -Path "C:\ Data\Response_Group_Call_List_Report.csv"
    $calls | Group-Object Workflow | Select-Object Count, Name | Sort-Object Count -Descending

Des informations analogues aux suivantes seront renvoyées :

    Count    Name
    -----    ----
      160    Redmond Help Desk
       47    Dublin Help Desk
       31    North America Customer Support
       16    EMEA Customer Support
       14    Employment Opportunities

## Filtres

Les filtres vous offrent la possibilité de renvoyer un ensemble de données mieux ciblées ou de visualiser les données renvoyées de différentes manières. Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport de liste des appels Response Group.

### Filtres de rapport de liste des appels Response Group

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
<p>07/07/2012 13:00</p>
<p>Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</p>
<p>07/07/2012</p>
<p>Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</p>
<p>7/3/2012</p>
<p>Les semaines s’étalent toujours du dimanche au samedi.</p></td>
</tr>
<tr class="even">
<td><p><strong>À</strong></p></td>
<td><p>Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :</p>
<p>07/07/2012 13:00</p>
<p>Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</p>
<p>07/07/2012</p>
<p>Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</p>
<p>7/3/2012</p>
<p>Les semaines s’étalent toujours du dimanche au samedi.</p></td>
</tr>
<tr class="odd">
<td><p><strong>URI du flux de travail</strong></p></td>
<td><p>Vous permet de limiter les données renvoyées au flux de travail Response Group spécifié. Pour utiliser ce filtre, entrez l’adresse SIP du flux de travail. Par exemple :</p>
<p>sip:helpdesk@litwareinc.com</p></td>
</tr>
<tr class="even">
<td><p><strong>Appels</strong></p></td>
<td><p>Vous pouvez sélectionner l’un des types d’appels suivants :</p>
<ul>
<li><p>Appels reçus</p></li>
<li><p>Appels réussis</p></li>
<li><p>Appels offerts</p></li>
<li><p>Appels ayant obtenu une réponse</p></li>
<li><p>Appels transférés</p></li>
</ul></td>
</tr>
</tbody>
</table>


## Mesures

Le tableau qui suit répertorie les informations fournies dans le rapport de liste des appels Response Group pour chaque appel reçu par l’application Response Group.

### Mesures du rapport de liste des appels Response Group

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
<td><p><strong>Caller</strong></p></td>
<td><p>Non</p></td>
<td><p>Adresse SIP de l’appelant.</p></td>
</tr>
<tr class="even">
<td><p><strong>Flux de travail</strong></p></td>
<td><p>Non</p></td>
<td><p>Adresse SIP du flux de travail Response Group.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Heure de début</strong></p></td>
<td><p>Non</p></td>
<td><p>Date et heure de début de l’appel.</p></td>
</tr>
<tr class="even">
<td><p><strong>Heure de fin</strong></p></td>
<td><p>Non</p></td>
<td><p>Date et heure de fin de l’appel.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Code de réponse</strong></p></td>
<td><p>Non</p></td>
<td><p>Code de réponse SIP envoyé lors de l’échec de session.</p></td>
</tr>
<tr class="even">
<td><p><strong>ID de diagnostic</strong></p></td>
<td><p>Non</p></td>
<td><p>Identifiant unique (sous la forme d’un en-tête ms-diagnostics) attaché à un message SIP qui procure souvent des informations utiles à des fins d’identification et de résolution des erreurs.</p></td>
</tr>
</tbody>
</table>

