---
title: "Pr. en ch. de la connect. PIC (Public IM Connectivity) dans Lync Server 2013"
TOCtitle: "Pr. en ch. de la connect. PIC (Public IM Connectivity) dans Lync Server 2013"
ms:assetid: 9c6eb500-647b-4ccd-a00e-2b8dd7c44a76
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn458579(v=OCS.15)
ms:contentKeyID: 59602877
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Prise en charge de la connectivité PIC (Public IM Connectivity) dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

## Prise en charge de la connectivité PIC (Public IM Connectivity)

Cet article fournit des informations sur la prise en charge de la connectivité PIC (Public IM Connectivity). Grâce à cette fonctionnalité de Microsoft Lync, les organisations peuvent permettre à leurs utilisateurs Lync de se connecter avec les utilisateurs de certains services de messagerie instantanée publics via leurs clients Lync et identités.

Les utilisateurs finaux peuvent ainsi se connecter avec des clients, des partenaires et des fournisseurs comme bon leur semble. Le service informatique assure le support d’un seul client de communication en temps réel, tout en gérant les fonctionnalités de contrôle, de conformité et d’archivage de Lync. La connectivité Lync-Skype, [disponible depuis mai 2013](http://blogs.technet.com/b/lync/archive/2013/05/23/lync-skype-connectivity-available-today.aspx) tire parti de l’héritage établi à l’origine par Lync/Office Communications Server (OCS)/Live Communications Server (LCS) avec la connectivité PIC via la connexion à MSN/Windows Live, AOL et Yahoo. Pour plus d’informations sur la connectivité Lync-Skype, voir la page [Connectivité Lync-Skype](http://office.microsoft.com/fr-fr/lync/lync-skype-connectivity-fx103789635.aspx). La fédération avec Windows Live, AOL et Yahoo approche de son terme. Cette page donne des informations sur le statut de chaque service.

Pour utiliser la connectivité PIC, les clients sont tenus d’activer le service pour chaque fournisseur de services de messagerie instantanée public. Les conditions requises et détails associés dépendent du fournisseur de services de messagerie instantanée public et du programme de licence sous-jacent du client.

## Windows Live Messenger

Microsoft a réuni Windows Live Messenger et Skype. En avril 2013, les utilisateurs Messenger ont été migrés vers Skype lors de leur connexion. Les clients Lync qui utilisent la fédération avec Messenger peuvent toujours communiquer avec leurs contacts Messenger, même après la mise à jour de ces contacts vers Skype. Les administrateurs ou utilisateurs Lync n’ont pas besoin de faire quoi que ce soit pour gérer la continuité du service. La gestion de cette fonctionnalité dans Lync reste la même que pour les communications avec Messenger.

Lorsque les utilisateurs Messenger se connectent à Skype à l’aide de leur compte Microsoft (avec les mêmes informations d’identification utilisées pour Messenger), leurs contacts Messenger, y compris les contacts Lync fédérés, sont disponibles dans Skype. Le partage de la présence et la messagerie instantanée entre Skype et Lync pour ces contacts sont disponibles.

La connectivité Lync-Skype (ajout de contacts, partage de la présence, messagerie instantanée et appel audio entre les utilisateurs Lync et Skype) est désormais accessible à tous les clients Lync.

## Yahoo\! et AOL Instant Messenger

La fédération avec Yahoo\! et AOL approche de son terme pour les clients de Lync (et Office Communications Server). La capacité de Microsoft à fournir ces services est conditionnée par le support de Yahoo\! et AOL. Or, les accords associés arrivent à leur fin. Pour Yahoo\! et AOL, le service sera maintenu jusqu’en juin 2014.

  - **Yahoo** : le service sera maintenu jusqu’en juin 2014. Les clients doivent toujours disposer de la licence Microsoft Lync « PIC USL » (Public IM Connectivity User Subscription License). Depuis le 1er septembre 2012, la licence PIC USL n’est plus disponible et ne peut pas être achetée ou renouvelée. Les clients ayant acheté une licence avant cette date pourront continuer à assurer la fédération avec Yahoo\! jusqu’à la date d’arrêt du service ou l’expiration de leur licence. Consultez l’[annonce](http://blogs.technet.com/b/lync/archive/2012/11/26/lync-and-yahoo-federation-end-of-life.aspx) sur le blog de l’équipe Lync. Les clients détenteurs de licences PIC dans le cadre d’accords valables au-delà du 30 juin 2014 recevront un crédit proportionnel au montant des paiements et destiné à couvrir la période suivant le 30 juin 2014.

  - **AOL** : le service de connectivité PIC de Lync ne sera plus disponible à partir du 30 juin 2014. Afin de limiter les perturbations au niveau des clients à la fin du service, nous avons interrompu l’approvisionnement de domaines client supplémentaires. Jusqu’au 30 juin 2014, les clients ne doivent pas faire quoi que ce soit pour continuer à prendre en charge les communications fédérées avec AIM. Au-delà de cette date (ou pour les clients qui souhaitent approvisionner d’autres domaines pendant cette période), un service de remplacement est disponible directement auprès d’AOL. Pour plus d’informations sur le nouveau service d’AOL, voir [Establishing Direct Federation with AIM (Établissement de la fédération directe avec AIM)](http://aimenterprise.aol.com/pic.php) (ce lien ouvre une nouvelle page sur AOL.com).

## Résumé des fournisseurs de messagerie instantanée publics

Le tableau suivant fournit un résumé des fournisseurs de messagerie instantanée publics, des fonctionnalités de fédération avec Lync et des licences requises.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Fournisseur de messagerie instantanée public</th>
<th>Fonctionnalités fédérées</th>
<th>Licences requises</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Skype</p></td>
<td><p>MI, présence, son</p></td>
<td><p>Licences d’accès client Lync Server, Lync Online - Plan 1/2/3</p></td>
</tr>
<tr class="even">
<td><p>Windows Live Messenger</p></td>
<td><p>Messagerie instantanée, présence, son/vidéo</p></td>
<td><p>Licences d’accès client Lync Server (prises en charge tant que WLM est commercialisé)</p></td>
</tr>
<tr class="odd">
<td><p>AOL</p></td>
<td><p>MI, présence</p></td>
<td><p>Licences d’accès client Lync Server (prises en charge jusqu’en juin 2014 pour les clients existants).</p></td>
</tr>
<tr class="even">
<td><p>Yahoo!</p></td>
<td><p>MI, présence</p></td>
<td><p>Nécessite des licences Microsoft Lync « PIC USL » (Public IM Connectivity User Subscription License) en plus des licences d’accès client Lync Server. Conformément à la liste de prix de septembre 2012, la licence PIC USL n’est plus disponible et ne peut pas être achetée. Les clients disposant de licences actives pourront continuer à assurer la fédération avec Yahoo! Messenger jusqu’à la date d’arrêt du service le 30 juin 2014.</p></td>
</tr>
</tbody>
</table>

