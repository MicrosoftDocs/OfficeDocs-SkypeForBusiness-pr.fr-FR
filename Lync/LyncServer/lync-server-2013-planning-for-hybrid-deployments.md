---
title: 'Lync Server 2013 : Planification des déploiements hybrides Lync Server'
TOCTitle: Planification des déploiements hybrides Lync Server
ms:assetid: f8b3d240-bc2e-42c9-acf8-d532d641a14c
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205403(v=OCS.15)
ms:contentKeyID: 49299394
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Planification des déploiements hybrides Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Lors de la planification d’un déploiement hybride, prenez en compte les éléments suivants pour votre infrastructure réseau et pour les utilisateurs.

## Conditions requises pour l’infrastructure

Les éléments suivants doivent être disponibles dans votre environnement afin d’implémenter et de configurer un déploiement hybride Lync Server 2013.

  - Un locataire Office 365 pour lequel Lync Online est activé.

  - Un serveur Active Directory Federation Services (AD FS) local ou utilisant Microsoft Azure. Pour plus d’informations sur Active Directory Federation Services (AD FS), reportez-vous à [Active Directory Federation Services 2.0](http://go.microsoft.com/fwlink/p/?linkid=393795) ou [Configurer Active Directory Federation Services pour Windows Azure Pack](http://go.microsoft.com/fwlink/p/?linkid=522475).

  - Un déploiement local de Lync Server 2013 ou Lync Server 2010 avec les mises à jour cumulatives pour Lync Server 2010 de mars 2013 ou ultérieures.

  - Outils d’administration de Lync Server 2013.

  - Synchronisation d’annuaire. Pour plus d’informations sur la synchronisation d’annuaire, reportez-vous à [Gestion des identités hybrides](http://go.microsoft.com/fwlink/p/?linkid=231010).

## Prise en charge du client Lync

Des différences existent dans les fonctionnalités prises en charge dans les clients Lync, ainsi que dans les fonctionnalités disponibles dans des environnements locaux et en ligne. Avant de choisir où vous voulez héberger les utilisateurs de votre organisation, vous pouvez consulter la prise en charge client pour les différentes configurations de Lync Server. Les clients suivants sont pris en charge avec Skype Entreprise Online dans un déploiement hybride Lync :

  - Lync 2010

  - Lync 2013

  - application Lync du Windows Store

  - Lync Web App

  - Lync Mobile

  - Lync pour Mac 2011

  - Lync Room System

  - Lync Basic 2013

Pour plus d’informations sur la prise en charge client, reportez-vous aux rubriques suivantes :

  - [Clients pour Lync Online](http://go.microsoft.com/fwlink/?linkid=281902)

  - [Tableau de comparaison des clients pour Lync Server 2013](lync-server-2013-desktop-client-comparison-tables.md)

  - [Tableau de comparaison des clients mobiles pour Lync Server 2013](lync-server-2013-mobile-client-comparison-tables.md)

## Conditions requises pour la topologie

Pour configurer votre déploiement Lync Server 2013 pour une utilisation hybride avec Skype Entreprise Online, l’une des topologies suivantes doit être prise en charge :

  - Microsoft Office Communications Server 2007 R2 avec Lync Server 2013 en local. La fédération Lync Server 2013serveur Edge et le serveur du tronçon suivant à partir du serveur Edge de fédération doit exécuter Lync Server 2013, et un Magasin central de gestion doit être déployé. Le serveur Edge et le pool doivent être déployés localement.
    
    > [!IMPORTANT]  
    > Même si cette topologie est prise en charge, certaines fonctionnalités peuvent être limitées. Par exemple, les informations de présence entre les utilisateurs Microsoft Lync Online et les utilisateurs Office Communications Server 2007 R2 locaux peuvent ne pas fonctionner comme prévu.

  - Microsoft Lync Server 2010 avec les mises à jour cumulatives pour Lync Server 2010 de mars 2013 appliqués (ou ultérieures) et outils d’administration de Lync Server 2013 installés en local. Le serveur Edge de fédération et le serveur de la jonction suivante du serveur Edge de fédération doivent exécuter Microsoft Lync Server 2010 avec les mises à jour cumulatives de mars 2013 (ou ultérieures) appliquées ou Lync Server 2013.
    
    > [!IMPORTANT]  
    > Les outils d’administration de Lync Server 2013 doivent être installés sur un serveur distinct pouvant se connecter au déploiement Lync Server 2010 existant. L’applet de commande Move-CsUser doit être exécutée à partir des outils d’administration de Lync Server 2013 connectés à votre déploiement local pour déplacer les utilisateurs de votre déploiement local vers Lync Online.

  - Un déploiement Lync Server 2013 avec tous les serveurs exécutant Lync Server 2013.

Pour plus d’informations sur les topologies prises en charge, reportez-vous à [Topologies prises en charge dans Lync Server 2013](lync-server-2013-supported-topologies.md) et à [Topologies de référence Lync Server 2013 pour les déploiements hybrides Enterprise](http://go.microsoft.com/fwlink/p/?linkid=398709).

Pour obtenir des informations d’identification et de résolution des problèmes liés aux déploiements hybrides et à la connexion de PowerShell à Lync Online, reportez-vous à [Lync Online: Lync PowerShell and Hybrid Troubleshooting (Lync Online : identification et résolution des problèmes liés à Lync PowerShell et aux déploiements hybrides)](http://go.microsoft.com/fwlink/p/?linkid=306718).

## Configuration requise pour les listes de fédération autorisées/bloquées

La liste des domaines autorisés comprend les domaines pour lesquels un nom complet Edge partenaire est configuré (parfois appelé *serveur partenaire autorisé* ou *partenaire de fédération direct* . Vous devez connaitre la différence entre la fédération ouverte et la fédération fermée, appelée *découverte de partenaire* et *liste de domaines partenaire autorisés* , dans les déploiements locaux.

La configuration suivante est requise pour configurer un déploiement hybride :

  - La correspondance de domaine doit être identique pour votre déploiement local et votre client Office 365. Si la découverte partenaire est activée sur le déploiement local; la fédération ouverte doit être configurée pour votre client en ligne. Si la découverte partenaire n’est pas activée, alors la fédération fermée doit être configurée pour votre client en ligne.

  - La liste des domaines bloqués dans le déploiement local doit correspondre exactement à la liste des domaines bloqués pour votre client en ligne.

  - La liste des domaines autorisés dans le déploiement local doit correspondre exactement à la liste des domaines autorisés pour votre client en ligne.

  - La fédération doit être activée pour les communications externes pour le client en ligne, qui est configurée à l’aide du panneau de configuration Lync Online.

## Paramètres DNS

Lors de la création des enregistrements DNS SRV pour les déploiements hybrides, les enregistrements, \_sipfederationtls.\_tcp.\<domaine\> et \_sip.\_tls.\<domaine\>, doivent pointer vers le proxy d’accès local.

## Éléments à prendre en compte pour le pare-feu

Les ordinateurs du réseau doivent être en mesure d’effectuer des recherches DNS Internet. Si ces ordinateurs peuvent accéder à des sites Internet standard, votre réseau est correctement configuré.

En fonction de l’emplacement de votre centre de données Microsoft Online Services, vous devez également configurer vos appareils de pare-feu réseau pour accepter les connexions en fonction de noms de domaine génériques (par exemple, tout le trafic de \*.outlook.com). Si les pare-feu de votre organisation ne prennent pas en charge les configurations de nom génériques, vous devrez déterminer manuellement les plages d’adresses IP que vous voulez autoriser et les ports.

Reportez-vous à la rubrique d’aide [URL et plages d’adresses IP Office 365](http://go.microsoft.com/fwlink/p/?linkid=252942).

## Configuration requise pour les ports et les protocoles

En plus de la configuration requise pour les ports pour les communications Lync Server 2013 internes, vous devez également configurer les ports suivants.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Protocole / Port</th>
<th>Applications</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TCP 443</p></td>
<td><p>Ouvrir entrant</p><ul><li><p>Active Directory Federation Services (rôle serveur de fédération)</p>
<p>Pour plus d’informations, reportez-vous à <a href="http://go.microsoft.com/fwlink/p/?linkid=281899">Présentation des services de rôle AD FS</a>.</p></li><li><p>Active Directory Federation Services (rôle serveur proxy)</p></li><li><p>Portail Microsoft Online Services</p></li><li><p>Mon portail d’entreprise</p></li><li><p>Outlook Web App</p></li><li><p>Client Lync (communications avec Lync Online à partir d’un Lync Server local)</p></li></ul></td>
</tr>
<tr class="even">
<td><p>TCP 80 et 443</p></td>
<td><p>Ouvrir entrant</p><ul><li><p>Outil de synchronisation d’annuaire Microsoft Online Services</p></li></ul></td>
</tr>
<tr class="odd">
<td><p>TCP 5061</p></td>
<td><p>Ouvrir entrant/sortant sur le serveur Edge</p></td>
</tr>
<tr class="even">
<td><p>PSOM/TLS 443</p></td>
<td><p>Ouvrir entrant/sortant pour les sessions de partage de données</p></td>
</tr>
<tr class="odd">
<td><p>STUN/TCP 443</p></td>
<td><p>Ouvrir entrant/sortant pour les sessions de partage audio, vidéo et d’applications</p></td>
</tr>
<tr class="even">
<td><p>STUN/UDP 3478</p></td>
<td><p>Ouvrir entrant/sortant pour les sessions audio et vidéo</p></td>
</tr>
<tr class="odd">
<td><p>RTP/TCP 50000-59999</p></td>
<td><p>Ouvrir sortant pour les sessions audio et vidéo</p></td>
</tr>
<tr class="even">
<td><p>TCP 443</p></td>
<td><p>Ouvrir entrant</p><ul><li><p>Active Directory Federation Services (rôle serveur de fédération)</p>
<p>Pour plus d’informations, reportez-vous à <a href="http://go.microsoft.com/fwlink/p/?linkid=281899">Présentation des services de rôle AD FS</a>.</p></li><li><p>Active Directory Federation Services (rôle serveur proxy)</p></li><li><p>Portail Microsoft Online Services</p></li><li><p>Mon portail d’entreprise</p></li><li><p>Outlook Web App</p></li><li><p>Client Lync (communications avec Lync Online à partir d’un Lync Server local)</p></li></ul></td>
</tr>
<tr class="odd">
<td><p>TCP 80 et 443</p></td>
<td><p>Ouvrir entrant</p><ul><li><p>Outil de synchronisation d’annuaire Microsoft Online Services</p></li></ul></td>
</tr>
<tr class="even">
<td><p>TCP 5061</p></td>
<td><p>Ouvrir entrant/sortant sur le serveur Edge</p></td>
</tr>
<tr class="odd">
<td><p>PSOM/TLS 443</p></td>
<td><p>Ouvrir entrant/sortant pour les sessions de partage de données</p></td>
</tr>
<tr class="even">
<td><p>STUN/TCP 443</p></td>
<td><p>Ouvrir entrant/sortant pour les sessions de partage audio, vidéo et d’applications</p></td>
</tr>
<tr class="odd">
<td><p>STUN/UDP 3478</p></td>
<td><p>Ouvrir entrant/sortant pour les sessions audio et vidéo</p></td>
</tr>
<tr class="even">
<td><p>RTP/TCP 50000-59999</p></td>
<td><p>Ouvrir sortant pour les sessions audio et vidéo</p></td>
</tr>
</tbody>
</table>


> [!NOTE]  
> Si vous avez besoin de la fédération avec les partenaires exécutant Office Communications Server 2007, vous devez ouvrir les ports entrant/sortant RTP/UDP et RTP/TCP 50000-59999. Pour plus d’informations sur les exigences liées au pare-feu A/V, reportez-vous à <a href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Définition de la configuration requise pour le pare-feu A/V et les ports pour Lync Server 2013</a>. Pour plus d’informations sur les ports et les protocoles, reportez-vous à <a href="lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md">Résumé des ports - Serveur Edge consolidé mis à l’échelle avec des équilibreurs de charge matérielle dans Lync Server 2013</a>.

## Comptes et données utilisateur

Dans un déploiement Lync Server 2013 hybride, tout utilisateur que vous voulez héberger dans Lync Online doit d’abord être créé dans le déploiement local afin que le compte utilisateur soit créé dans services de domaine Active Directory. Vous pouvez ensuite déplacer l’utilisateur vers Skype Entreprise Online, ce qui déplace la liste des contacts de l’utilisateur.

Lorsque vous synchronisez des comptes utilisateur entre les déploiements Lync locaux et Lync Online avec AD FS et Dirsync, vous devez synchroniser les comptes Active Directory pour tous les utilisateurs Lync de votre organisation entre vos déploiements Lync locaux et en ligne, même si les utilisateurs ne sont pas déplacés vers Lync Online. Si vous ne synchronisez pas tous les utilisateurs, la communication entre les utilisateurs locaux et en ligne dans votre organisation risque de ne pas fonctionner comme vous le souhaitez.

> [!IMPORTANT]  
> Si l’utilisateur est créé à l’aide du portail en ligne pour Office 365, le compte utilisateur ne sera pas synchronisé avec Active Directory en local où cet utilisateur ne figurera pas. Si vous avez déjà créé des utilisateurs dans Lync Online et que vous souhaitez configurer le déploiement hybride avec le déploiement Lync Server local, reportez-vous à <a href="lync-server-2013-moving-users-from-lync-online-to-lync-on-premises.md">Déplacement des utilisateurs de Lync Online vers Lync local dans Lync Server 2013</a>.

Prenez en compte les problèmes suivants liés aux utilisateurs lors de la planification d’un déploiement hybride.

  - **Contacts de l’utilisateur**   Le nombre maximal de contacts pour les utilisateurs Lync Online est de 250. Au-delà de ce chiffre, les contacts seront supprimés de la liste des contacts de l’utilisateur.

  - **Messagerie instantanée et présence**   Les listes de contacts, groupes et listes de contrôle d’accès des utilisateurs sont migrés avec le compte de l’utilisateur.

  - **Données de conférence, contenu de réunion et réunions planifiées**   Ce contenu n’est pas migré avec le compte de l’utilisateur. Les utilisateurs doivent replanifier les réunions une fois leur compte migré sur Lync Online.

## Fonctionnalités et stratégies utilisateur

  - Dans un environnement Lync Server 2013 hybride, les utilisateurs peuvent utiliser la messagerie instantanée, la voix et les réunions soit localement soir en ligne, mais les deux simultanément.

  - **Client Lync**    Certains utilisateurs peuvent avoir besoin d’une nouvelle version du client après leur déplacement vers Lync Online. Pour Office Communications Server 2007 R2, les utilisateurs doivent être déplacés vers un pool Lync Server 2013 avant la migration vers Lync Online.
    
    Pour plus d’informations sur la prise en charge de client, reportez-vous à [Clients for Lync Online (Clients pour Lync Online)](http://go.microsoft.com/fwlink/p/?linkid=281902) et [Supported Lync clients and network port configurations (Configurations des ports réseau et clients Lync pris en charge)](http://go.microsoft.com/fwlink/p/?linkid=281901) .

  - **Configuration et stratégies locales (non utilisateur)**   Les stratégies en ligne et locales nécessitent des configurations distinctes. Vous ne pouvez pas définir des stratégies globales qui s’appliquent au deux.

