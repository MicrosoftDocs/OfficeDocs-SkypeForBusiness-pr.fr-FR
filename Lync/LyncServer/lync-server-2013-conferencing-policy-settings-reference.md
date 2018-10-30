---
title: Référence des paramètres de stratégie de conférence pour Lync Server 2013
TOCTitle: Référence des paramètres de stratégie de conférence pour Lync Server 2013
ms:assetid: ec8125f7-ef78-4a2b-8db0-4dd3cf5a4065
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg429724(v=OCS.15)
ms:contentKeyID: 49299226
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Référence des paramètres de stratégie de conférence pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2014-04-22_

Les tableaux présentés ici répertorient tous les paramètres de stratégie de conférence que vous pouvez spécifier à l’aide du Panneau de configuration Lync Server 2013.

## Paramètres de stratégie de l’organisateur

Le tableau suivant répertorie tous les paramètres de stratégie de conférence que vous pouvez appliquer aux organisateurs de conférence. Pour obtenir la liste la plus à jour des paramètres de stratégie de conférence, voir la rubrique d'aide pour l'applet de commande [Set-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPolicy).

### Paramètres de stratégie de l’organisateur

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Paramètre</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Taille maximale de la réunion</p></td>
<td><p>Définit le nombre maximum de participants autorisés dans un réunion.</p></td>
</tr>
<tr class="even">
<td><p>Autoriser les participants à inviter des utilisateurs anonymes</p></td>
<td><p>Autorise les organisateurs de réunion à inviter des utilisateurs non authentifiés aux réunions.</p></td>
</tr>
<tr class="odd">
<td><p>Activer l’enregistrement</p></td>
<td><p>Autorise les présentateurs ou les participants à enregistrer la réunion.</p></td>
</tr>
<tr class="even">
<td><p>Autoriser les participants fédérés et anonymes à enregistrer</p></td>
<td><p>Autorise les participants externes et non authentifiés à enregistrer la réunion.</p></td>
</tr>
<tr class="odd">
<td><p>Activer Audio sur IP</p></td>
<td><p>Autorise l’utilisation du son dans une réunion.</p></td>
</tr>
<tr class="even">
<td><p>Activer l’audio/la vidéo IP</p></td>
<td><p>Autorise l’utilisation du son et de la vidéo dans une réunion.</p></td>
</tr>
<tr class="odd">
<td><p>Activer la conférence rendez-vous PSTN</p></td>
<td><p>Autorise l’utilisateur à participer à une réunion en numérotant à partir d’un réseau téléphonique commuté (PSTN).</p></td>
</tr>
<tr class="even">
<td><p>Autoriser l’accès sortant des participants anonymes</p></td>
<td><p>Autorise les utilisateurs non authentifiés à participer à une réunion à l’aide d’un appel sortant. Avec l’appel téléphonique sortant, le serveur de conférence appelle l’utilisateur et celui-ci répond au téléphone pour rejoindre la réunion.</p></td>
</tr>
<tr class="odd">
<td><p>Résolution vidéo maximale autorisée pour la conférence</p></td>
<td><p>Définit la résolution maximale pour la visioconférence. Les valeurs valides sont <strong>640*480(VGA)</strong> et <strong>352*288(CIF)</strong>.</p></td>
</tr>
<tr class="even">
<td><p>Activer la collaboration de données</p></td>
<td><p>Active les conférences de collaboration de données ou Web.</p></td>
</tr>
<tr class="odd">
<td><p>Autoriser les participants fédérés et anonymes à télécharger du contenu</p></td>
<td><p>Autorise les participants externes et non authentifiés à télécharger du contenu de la réunion.</p></td>
</tr>
<tr class="even">
<td><p>Autoriser les participants à transférer des fichiers</p></td>
<td><p>Autorise les participants à transférer des fichiers pendant une réunion.</p></td>
</tr>
<tr class="odd">
<td><p>Activer les annotations</p></td>
<td><p>Autorise les participants à la réunion à créer des annotations dans le contenu.</p></td>
</tr>
<tr class="even">
<td><p>Activer les sondages</p></td>
<td><p>Autorise les participants à la réunion à faire un sondage pendant une réunion.</p></td>
</tr>
<tr class="odd">
<td><p>Activer le partage d’application</p></td>
<td><p>Autorise les utilisateurs à planifier des réunions qui prennent en charge le partage d’application.</p></td>
</tr>
<tr class="even">
<td><p>Autoriser les participants à prendre le contrôle</p></td>
<td><p>Autorise les participants à prendre le contrôle d’une application partagée d’un autre utilisateur.</p></td>
</tr>
<tr class="odd">
<td><p>Autoriser les participants fédérés et anonymes à prendre le contrôle</p></td>
<td><p>Autorise les participants externes et anonymes à prendre le contrôle d’une application partagée d’un autre utilisateur.</p>

> [!NOTE]  
> Si ce paramètre est défini sur True et si <strong>Autoriser les participants à prendre le contrôle</strong> est défini sur False, ce paramètre est remplacé.

</td>
</tr>
</tbody>
</table>


## Paramètres de stratégie du participant

Le tableau suivant répertorie tous les paramètres de stratégie de conférence que vous pouvez appliquer aux participants à une conférence.

### Paramètres de stratégie du participant

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Paramètre</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Activer le partage d’application</p></td>
<td><p>Autorise les utilisateurs à planifier des réunions qui prennent en charge le partage d’application.</p></td>
</tr>
<tr class="even">
<td><p>Activer le partage d’application et de Bureau</p></td>
<td><p>Autorise les utilisateurs à participer à des réunions qui prennent en charge le partage d’application et de Bureau. Lors d’une conférence, la valeur de ce paramètre qui s’applique à l’organisateur de la conférence est appliquée à tous les systèmes d’extrémité anonymes qui participent également.</p></td>
</tr>
<tr class="odd">
<td><p>Autoriser le transfert de fichiers entre homologues</p></td>
<td><p>Autorise les participants à transférer des fichiers entre homologues pendant une réunion. Un transfert de fichiers entre homologues n’implique pas tous les participants à la réunion.</p></td>
</tr>
<tr class="even">
<td><p>Activer l’enregistrement entre homologues</p></td>
<td><p>Autorise les participants à enregistrer des sessions de conférence entre homologues.</p></td>
</tr>
</tbody>
</table>

