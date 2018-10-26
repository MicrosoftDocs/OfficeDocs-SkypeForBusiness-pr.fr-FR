---
title: 'Lync Server 2013 : Prise en charge du logiciel client Lync'
TOCTitle: Prise en charge du logiciel client Lync
ms:assetid: a6851e38-ba9a-4f19-9aa7-d8accf4d62b3
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg412781(v=OCS.15)
ms:contentKeyID: 49298425
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Prise en charge du logiciel client Lync dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Cette section fournit une synthèse de la prise en charge logicielle pour Lync 2013 et le complément de réunion en ligne pour Lync 2013.

> [!NOTE]  
> Le complément de réunion en ligne pour Lync 2013, qui permet de gérer les réunions à partir du client de messagerie et de collaboration Outlook s’installe automatiquement avec Lync 2013.

### Configuration logicielle requise pour Lync 2013 et le complément de réunion en ligne pour Lync 2013

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Composant système</th>
<th>Spécification minimale</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Système d’exploitation Windows</p></td>
<td><p>Windows 8.1</p>
<p>Windows 8</p>
<p>système d’exploitation Windows 7</p>
<p>Windows Server 2008 R2 avec le Service Pack le plus récent</p>
<div>

> [!NOTE]  
> Lync 2013 et complément de réunion en ligne pour Lync 2013 ne sont pas pris en charge sur Windows Vista ni sur Windows XP (toutes versions).
</div></td>
</tr>
<tr class="even">
<td><p>Installation et mises à jour</p></td>
<td><p>Droits et autorisations d’administrateur</p></td>
</tr>
<tr class="odd">
<td><p>Navigateur</p></td>
<td><p>Navigateur Internet Windows Internet Explorer 10</p>
<p>Navigateur Internet Internet Explorer 9</p>
<p>Navigateur Internet Internet Explorer 8</p>
<p>Navigateur Internet Internet Explorer 7</p>
<p>Navigateur web Mozilla Firefox</p>
<div>

> [!NOTE]  
> Si vous utilisez Lync avec Microsoft Exchange Online et que votre organisation a déployé un proxy HTTP d’authentification, Internet Explorer 9 ou Internet Explorer 8 est requis.
</div></td>
</tr>
<tr class="even">
<td><p>Intégration à Microsoft Office</p></td>
<td><p>Pour le jeu complet de fonctionnalités d’intégration :</p><ul><li><p>Client de messagerie et de collaboration Outlook 2013</p></li><li><p>Client de messagerie et de collaboration Outlook 2010</p></li></ul></td>
</tr>
<tr class="odd">
<td><p>Intégration à Microsoft Exchange</p></td>
<td><p>Pour le jeu complet de fonctionnalités d’intégration :</p><ul><li><p>Microsoft Exchange Server 2013</p></li><li><p>Microsoft Exchange Server 2010</p></li></ul></td>
</tr>
</tbody>
</table>


## Systèmes d’exploitation Macintosh

Lync 2013 est disponible uniquement pour Windows. Cependant, Lync Server 2013 prend en charge les clients suivants sur les ordinateurs qui exécutent un système d’exploitation Mac OS 10.5.8 ou une version ou un Service Pack plus récent (basé sur Intel) (le système d’exploitation Mac OS 10.9 n’est pas pris en charge actuellement). Pour plus d’informations sur les fonctionnalités prises en charge, reportez-vous à [Tableau de comparaison des clients pour Lync Server 2013](lync-server-2013-desktop-client-comparison-tables.md).

  - Microsoft Lync pour Mac 2011 (reportez-vous au « Guide de déploiement de Lync pour Mac 2011 » à l’adresse [http://go.microsoft.com/fwlink/?linkid=268786\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=268786%26clcid=0x40c))

  - Microsoft Communicator pour Mac 2011 (reportez-vous au « Guide de déploiement de Communicator pour Mac 2011 » à l’adresse [http://go.microsoft.com/fwlink/?linkid=268787\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=268787%26clcid=0x40c))

## Navigateurs Lync Web App

Lync Web App prend en charge des combinaisons spécifiques de systèmes d’exploitation et de navigateurs. Pour plus d’informations, reportez-vous au [Plateformes prises en charge par Lync Web App pour Lync Server 2013](lync-server-2013-lync-web-app-supported-platforms.md) dans la documentation de planification.

## Capacité de prise en charge de Microsoft Office

Les clients Lync Server 2013 prennent en charge l’intégration à diverses versions de Microsoft Office, comme résumé dans cette section.

  - Les fonctionnalités d’intégration de Lync 2013 sont prises en charge sur Outlook 2013 et Microsoft Outlook 2010.

  - Les fonctionnalités d’intégration de Lync 2013 sont prises en charge sur Microsoft Exchange Server 2013 et Microsoft Exchange Server 2010.

  - Le complément Réunion en ligne pour Lync 2013 est pris en charge avec Office 2013 et Microsoft Office 2010.

## Utilisation de profils obligatoires

Si des utilisateurs prévoient d’utiliser les fonctionnalités de conférence de Lync 2013, ils ne doivent pas utiliser de profils obligatoires des services de domaine Active Directory pour se connecter au client Lync 2013. Les profils obligatoires étant des profils utilisateur en lecture seule, les clés d’Infrastructure à clé publique (PKI, Public Key Infrastructure) requises pour les conférences Lync 2013 ne peuvent pas être enregistrées dans le profil. Pour plus d’informations, reportez-vous à l’article 2552221 de la Base de connaissances Microsoft intitulé « La fonctionnalité de conférence de Lync 2010 échoue lorsqu’un utilisateur est connecté avec un profil utilisateur obligatoire » à l’adresse [http://go.microsoft.com/fwlink/?linkid=3052\&clcid=0x40C](http://go.microsoft.com/fwlink/?linkid=3052%26clcid=0x40c).

## Voir aussi

#### Concepts

[Prise en charge du matériel client Lync dans Lync Server 2013](lync-server-2013-lync-client-hardware-support.md)  
[Configuration requise pour la vidéo du client Skype Entreprise pour Skype Entreprise Server 2015](lync-server-2013-lync-client-video-requirements.md)  
[Clients pris en charge provenant d’anciens déploiements dans Lync Server 2013](lync-server-2013-supported-clients-from-previous-deployments.md)

