---
title: "Exp. de Response Group en cas de défaillance d’un pool dans Lync Server 2013"
TOCTitle: Expérience de Response Group en cas de défaillance d’un pool
ms:assetid: 4e00fb38-64b1-4fd9-903d-7639177bc303
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204886(v=OCS.15)
ms:contentKeyID: 49297163
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Expérience de Response Group en cas de défaillance d’un pool dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Cette section décrit en détail la façon dont l’activité des groupes Response Group est affectée au cours des étapes suivantes :

  - Une panne se produit dans le pool principal, mais le basculement n’est pas encore démarré.

  - Un basculement du service est effectué vers le pool de sauvegarde.

  - Une restauration automatique du service est effectuée vers le pool principal.

## Expérience utilisateur en cas de panne

Quand une panne se produit au niveau d’un pool ou d’un site mais que l’administrateur n’a pas encore effectué de basculement, l’activité des groupes Response Group est gérée comme indiqué dans le tableau suivant.

> [!NOTE]  
> Au cours d’une récupération d’urgence, les appels se comportent différemment si les groupes Response Group du pool principal ont été importés dans le pool de sauvegarde au cours de la récupération d’urgence. Dans le tableau suivant, les références vers les groupes Response Group importés indiquent que les groupes Response Group du pool principal ont été importés dans le pool de sauvegarde en mode récupération d’urgence.

### Situation de panne

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Type d’appel ou action de l’utilisateur</th>
<th>Pendant une panne</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Appels connectés à un agent</p></td>
<td><ul><li><p>Les appels normaux restent connectés.</p></li><li><p>Les appels anonymes sont déconnectés.</p></li></ul></td>
</tr>
<tr class="even">
<td><p>Appels en cours pas encore connectés à un agent</p></td>
<td><p>Les appels sont déconnectés.</p></td>
</tr>
<tr class="odd">
<td><p>Nouveaux appels</p></td>
<td><ul><li><p>Les appels sont déconnectés.</p></li><li><p>Si des groupes Response Group sont importés, les appels se connectent au pool de sauvegarde mais les agents hébergés dans le pool principal sont injoignables.</p></li></ul></td>
</tr>
<tr class="even">
<td><p>L’agent appelle pour le compte du groupe Response Group</p></td>
<td><p>La fonctionnalité est désactivée au cours de cette étape.</p></td>
</tr>
<tr class="odd">
<td><p>Connexion et informations de l’agent</p></td>
<td><ul><li><p>Les groupes d’agents que possède le pool principal sont consultables sur la console des agents mais les agents ne peuvent pas se connecter.</p></li><li><p>Les groupes d’agents que possède le pool de sauvegarde sont consultables sur la console des agents et les agents peuvent se connecter.</p></li><li><p>Les groupes d’agents importés ne sont pas affichés dans la console des agents.</p></li></ul></td>
</tr>
<tr class="even">
<td><p>Configuration des groupes Response Group</p></td>
<td><ul><li><p>Les groupes Response Group que possède le pool principal sont consultables en fonction de la disponibilité de la base de données principale du pool principal, mais ils ne sont pas modifiables.</p></li><li><p>Les groupes Response Group que possède le pool de sauvegarde sont consultables et modifiables.</p></li><li><p>Il n’est pas possible de consulter les groupes Response Group importés avec le Panneau de configuration Lync Server ou l’outil de configuration Response Group, mais il est possible de les configurer à l’aide des applets de commande Lync Server Management Shell.</p></li></ul></td>
</tr>
</tbody>
</table>


## Expérience utilisateur durant le basculement

Quand un administrateur a recours au basculement vers un pool de sauvegarde, l’activité des groupes Response Group est gérée pendant et après le basculement comme indiqué dans le tableau suivant. La première colonne décrit le type d’activité qui peut avoir lieu. La colonne du milieu décrit la façon dont chaque activité est gérée durant le bref laps de temps nécessaire au basculement vers le pool de sauvegarde. La dernière colonne décrit la façon dont l’activité est gérée pendant toute la durée de l’opération, une fois que le processus de basculement est terminé et que le pool de sauvegarde a remplacé le pool principal.

> [!NOTE]  
> Au cours d’une récupération d’urgence, les appels se comportent différemment si les groupes Response Group du pool principal ont été importés dans le pool de sauvegarde au cours de la récupération d’urgence. Dans le tableau suivant, les références vers les groupes Response Group importés indiquent que les groupes Response Group du pool principal ont été importés dans le pool de sauvegarde en mode récupération d’urgence.

### Basculement démarré

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Type d’appel ou action de l’utilisateur</th>
<th>Durant le basculement</th>
<th>Une fois le basculement terminé</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Appels connectés à un agent</p></td>
<td><ul><li><p>Les appels normaux restent connectés.</p></li><li><p>Les appels anonymes sont déconnectés.</p></li></ul></td>
<td><ul><li><p>Les appels normaux restent connectés.</p></li><li><p>Pour les groupes Response Group importés, les appels anonymes qui ont joint le pool de sauvegarde restent connectés.</p></li></ul></td>
</tr>
<tr class="even">
<td><p>Appels en cours pas encore connectés à un agent</p></td>
<td><p>Les appels sont déconnectés.</p></td>
<td><ul><li><p>Si aucun groupe Response Group n’a été importé, il n’y a aucun appel avec cet état.</p></li><li><p>Pour les groupes Response Group importés, les appels qui ont joint le pool de sauvegarde restent connectés.</p></li></ul></td>
</tr>
<tr class="odd">
<td><p>Nouveaux appels</p></td>
<td><ul><li><p>Les appels sont déconnectés.</p></li><li><p>Pour les groupes Response Group importés, les appels se connectent au pool de sauvegarde mais les agents hébergés dans le pool principal sont injoignables.</p></li></ul></td>
<td><ul><li><p>Si les groupes Response Group n’ont pas été importés, les appels sont déconnectés.</p></li><li><p>Pour les groupes Response Group importés, les appels se connectent au pool de sauvegarde.</p></li></ul></td>
</tr>
<tr class="even">
<td><p>L’agent appelle pour le compte du groupe Response Group</p></td>
<td><p>La fonctionnalité est désactivée au cours de cette étape.</p></td>
<td><ul><li><p>Si les groupes Response Group n’ont pas été importés, les appels n’aboutissent pas.</p></li><li><p>Pour les groupes Response Group importés, les appels aboutissent.</p></li></ul></td>
</tr>
<tr class="odd">
<td><p>Connexion et informations de l’agent</p></td>
<td><ul><li><p>Les groupes d’agents que possède le pool principal sont consultables sur la console des agents mais les agents ne peuvent pas se connecter.</p></li><li><p>Les groupes d’agents que possède le pool de sauvegarde sont consultables sur la console des agents et les agents peuvent se connecter.</p></li><li><p>Les groupes d’agents importés sont affichés dans la console des agents et les agents peuvent se connecter.</p></li></ul></td>
<td><ul><li><p>Les groupes d’agents que possède le pool principal sont consultables sur la console des agents mais les agents ne peuvent pas se connecter.</p></li><li><p>Les groupes d’agents que possède le pool de sauvegarde sont consultables sur la console des agents et les agents peuvent se connecter.</p></li><li><p>Les groupes d’agents importés sont affichés dans la console des agents et les agents peuvent se connecter.</p></li></ul></td>
</tr>
<tr class="even">
<td><p>Configuration des groupes Response Group</p></td>
<td><ul><li><p>Les groupes Response Group que possède le pool principal sont consultables en fonction de la disponibilité de la base de données principale du pool principal, mais ils ne sont pas modifiables.</p></li><li><p>Les groupes Response Group que possède le pool de sauvegarde sont consultables et modifiables.</p></li><li><p>Il n’est pas possible de consulter les groupes Response Group importés avec le Panneau de configuration Lync Server ou l’outil de configuration Response Group, mais il est possible de les configurer à l’aide des applets de commande Lync Server Management Shell.</p></li></ul></td>
<td><ul><li><p>Les groupes Response Group que possède le pool principal sont consultables en fonction de la disponibilité de la base de données principale, mais ils ne sont pas modifiables.</p></li><li><p>Les groupes Response Group que possède le pool de sauvegarde sont consultables et modifiables.</p></li><li><p>Il n’est pas possible de consulter les groupes Response Group importés avec le Panneau de configuration Lync Server ou l’outil de configuration Response Group, mais il est possible de les configurer à l’aide des applets de commande Lync Server Management Shell.</p></li></ul></td>
</tr>
</tbody>
</table>


## Expérience utilisateur durant la restauration

Quand un administrateur a recours à la restauration automatique vers le pool principal, l’activité des groupes Response Group est gérée pendant et après la restauration automatique comme indiqué dans le tableau suivant.

> [!NOTE]  
> Au cours d’une récupération d’urgence, les appels se comportent différemment si les groupes Response Group du pool principal ont été importés dans le pool de sauvegarde au cours de la récupération d’urgence. Dans le tableau suivant, les références vers les groupes Response Group importés indiquent que les groupes Response Group du pool principal ont été importés dans le pool de sauvegarde en mode récupération d’urgence.

### Gestion des appels pendant la restauration automatique

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Type d’appel ou action de l’utilisateur</th>
<th>Pendant la restauration automatique</th>
<th>Une fois la restauration automatique terminée</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Appels connectés à un agent</p></td>
<td><ul><li><p>Les appels normaux restent connectés.</p></li><li><p>Si aucun groupe Response Group n’a été importé, il n’y a aucun appel anonyme avec cet état.</p></li><li><p>Pour les groupes Response Group importés, les appels anonymes restent connectés.</p></li></ul></td>
<td><ul><li><p>Les appels normaux restent connectés.</p></li><li><p>Si aucun groupe Response Group n’a été importé, il n’y a aucun appel anonyme avec cet état.</p></li><li><p>Pour les groupes Response Group importés, les appels anonymes restent connectés.</p></li></ul></td>
</tr>
<tr class="even">
<td><p>Appels en cours pas encore connectés à un agent</p></td>
<td><ul><li><p>Si aucun groupe Response Group n’a été importé, il n’y a aucun appel avec cet état.</p></li><li><p>Pour les groupes Response Group importés, les appels seront déconnectés.</p></li></ul></td>
<td><ul><li><p>Si aucun groupe Response Group n’a été importé, il n’y a aucun appel avec cet état.</p></li><li><p>Pour les groupes Response Group importés, les appels seront déconnectés.</p></li></ul></td>
</tr>
<tr class="odd">
<td><p>Nouveaux appels</p></td>
<td><p>Les appels se connectent au pool principal mais les agents hébergés dans le pool principal sont injoignables.</p></td>
<td><p>Les appels se connectent au pool principal.</p></td>
</tr>
<tr class="even">
<td><p>L’agent appelle pour le compte du groupe Response Group</p></td>
<td><p>La fonctionnalité est désactivée au cours de cette étape.</p></td>
<td><p>Les appels aboutissent.</p></td>
</tr>
<tr class="odd">
<td><p>Connexion et informations de l’agent</p></td>
<td><ul><li><p>Les groupes d’agents que possède le pool principal sont consultables sur la console des agents mais les agents ne peuvent pas se connecter.</p></li><li><p>Les groupes d’agents que possède le pool de sauvegarde sont consultables sur la console des agents et les agents peuvent se connecter.</p></li><li><p>Les groupes d’agents importés sont affichés dans la console des agents et les agents peuvent se connecter.</p></li></ul></td>
<td><ul><li><p>Les groupes d’agents que possède le pool principal sont consultables sur la console des agents et les agents peuvent se connecter.</p></li><li><p>Les groupes d’agents que possède le pool de sauvegarde sont consultables sur la console des agents et les agents peuvent se connecter.</p></li><li><p>Les groupes d’agents importés ne sont pas affichés dans la console des agents.</p></li></ul></td>
</tr>
<tr class="even">
<td><p>Configuration des groupes Response Group</p></td>
<td><ul><li><p>Les groupes Response Group que possède le pool principal sont consultables en fonction de la disponibilité de la base de données principale du pool principal, mais ils ne sont pas modifiables.</p></li><li><p>Les groupes Response Group que possède le pool de sauvegarde sont consultables et modifiables.</p></li><li><p>Il n’est pas possible de consulter les groupes Response Group importés avec le Panneau de configuration Lync Server ou l’outil de configuration Response Group, mais il est possible de les configurer à l’aide des applets de commande Lync Server Management Shell.</p></li></ul></td>
<td><ul><li><p>Les groupes Response Group que possède le pool principal sont consultables et modifiables.</p></li><li><p>Les groupes Response Group que possède le pool de sauvegarde sont consultables et modifiables.</p></li><li><p>Il n’est pas possible de consulter les groupes Response Group importés avec le Panneau de configuration Lync Server ou l’outil de configuration Response Group, mais il est possible de les configurer à l’aide des applets de commande Lync Server Management Shell.</p></li></ul></td>
</tr>
</tbody>
</table>

