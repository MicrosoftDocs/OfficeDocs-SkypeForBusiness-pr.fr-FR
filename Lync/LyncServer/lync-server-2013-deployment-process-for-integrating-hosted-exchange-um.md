---
title: "Lync Server 2013 : Pro. de dépl. pour l’int. de la mess. Un. Exchange hébergée"
TOCTitle: Processus de déploiement pour l’intégration de la messagerie unifiée Exchange hébergée à Lync Server
ms:assetid: dbec9c38-7f66-419d-b8c3-c61380052cac
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398968(v=OCS.15)
ms:contentKeyID: 49299036
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Processus de déploiement pour l’intégration de la messagerie unifiée Exchange hébergée à Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Pour planifier efficacement l’intégration de Lync Server 2013 à la messagerie unifiée Exchange hébergée, vous devez tenir compte des points suivants :

  - Conditions préalables à l’intégration de Lync Server 2013 à la messagerie unifiée Exchange hébergée

  - Étapes requises au cours du processus d’intégration

## Conditions préalables au déploiement pour l’intégration à la messagerie unifiée Exchange hébergée

Avant d’entamer le processus d’intégration, vous devez avoir déployé Lync Server 2013 (un pool frontal ou un serveur Standard Edition Server au moins), un serveur Edge et les clients Lync 2013 ou Lync 2010.

## Processus d’intégration

Le tableau ci-dessous présente une vue d’ensemble du processus d’intégration de la messagerie unifiée Exchange hébergée. Pour plus d’informations sur les étapes de déploiement, reportez-vous à [Mise à disposition de la messagerie vocale Lync Server 2013 aux utilisateurs sur la messagerie unifiée Exchange hébergée](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md) dans la documentation de déploiement.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Phase</th>
<th>Étapes</th>
<th>Droits et autorisations</th>
<th>Documentation de déploiement</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Configurez le serveur Edge.</p></td>
<td><ol>
<li><p>Configurez le serveur Edge pour la fédération.</p></li>
<li><p>Répliquez manuellement les données sur le serveur Edge.</p></li>
<li><p>Configurez le fournisseur d’hébergement sur le serveur Edge.</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">Configuration du serveur Edge pour l’intégration à la messagerie unifiée Exchange hébergée</a></p></td>
</tr>
<tr class="even">
<td><p>Configurez la stratégie de messagerie vocale hébergée.</p></td>
<td><ol>
<li><p>Modifiez la stratégie globale de messagerie vocale hébergée ou créez une stratégie de messagerie vocale hébergée avec une étendue de site ou par utilisateur.</p></li>
<li><p>Lorsque les stratégies sont définies avec une étendue par utilisateur, attribuez-les à des utilisateurs ou à des groupes.</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">Gestion des stratégies de messagerie vocale hébergée dans Lync Server 2013</a></p></td>
</tr>
<tr class="odd">
<td><p>Activez les utilisateurs pour la messagerie vocale hébergée.</p></td>
<td><ul>
<li><p>Configurez les comptes des utilisateurs qui possèdent des boîtes aux lettres sur un service Exchange hébergé.</p></li>
</ul></td>
<td><p>RTCUniversalUserAdmins</p></td>
<td><p><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">Activation des utilisateurs pour la messagerie vocale hébergée dans Lync Server 2013</a></p></td>
</tr>
<tr class="even">
<td><p>Configurez les objets contact hébergés.</p></td>
<td><ol>
<li><p>Créez des objets contact de standard automatique pour la messagerie unifiée Exchange hébergée.</p></li>
<li><p>Créez des objets contact d’accès abonné pour la messagerie unifiée Exchange hébergée.</p></li>
</ol></td>
<td><p>RTCUniversalUserAdmins</p>

> [!NOTE]  
> Pour créer, modifier ou supprimer des objets contact, l’utilisateur qui exécute l’applet de commande New-CsExUmContact, Set-CsExUmContact ou Remove-CsExUmContact doit posséder l’autorisation appropriée sur l’unité d’organisation Active Directory où sont stockés les nouveaux objets contact. Cette autorisation peut être accordée en exécutant l’applet de commande Grant-CsOUPermission. Pour plus d’informations, reportez-vous à la documentation relative à Lync Server Management Shell.

</td>
<td><p><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">Création des objets de contact pour la messagerie unifiée Exchange hébergée dans Lync Server 2013</a></p></td>
</tr>
</tbody>
</table>

