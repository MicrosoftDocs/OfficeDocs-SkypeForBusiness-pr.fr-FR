---
title: Sites Lync Server 2013
TOCTitle: Sites
ms:assetid: 022cb6dd-37e2-4882-a53e-5ddfdbc6f53a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398076(v=OCS.15)
ms:contentKeyID: 49296067
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Sites Lync Server pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-16_

Lync Server vous permet de définir les *sites* sur votre réseau qui contiennent des composants Lync Server. Un site désigne un ensemble d’ordinateurs connectés comme il se doit par un réseau haut débit à faible latence, par exemple, un réseau local unique (LAN) ou bien deux réseaux connectés via un réseau haut débit à fibre optique. Notez que les sites Lync Server sont un concept distinct des sites services de domaine Active Directory et des sites Microsoft Exchange Server. Les sites Lync Server ne doivent pas obligatoirement correspondre aux sites Active Directory.

## Types de site

Chaque site est soit un *site central* , qui contient au moins un pool de serveurs frontaux ou un serveur Standard Edition, soit un *site de succursale* . Chaque site de succursale est associé à exactement un site central et les utilisateurs du site de succursale obtiennent la plupart des fonctionnalités de Lync Server des serveurs situés sur le site central associé.

Chaque site de succursale contient l’un des éléments suivants :

  - Un *Survivable Branch Appliance* , qui est un serveur lame (blade) standard avec un serveur d’inscriptions et de médiation Lync Server fonctionnant sur Windows Server 2008. Le Survivable Branch Appliance contient également une passerelle de réseau téléphonique commuté (RTC). Le Survivable Branch Appliance est conçu pour les sites de succursale comptant entre 25 et 1 000 utilisateurs.

  - Un *serveur Survivable Branch Server (SBS)* , qui est un serveur exécutant Windows Server et qui répond à la configuration matérielle spécifiée et sur lequel le logiciel du serveur d’inscriptions et de médiation Lync Server est installé. Il doit se connecter à une passerelle RTC ou à une jonction SIP à un fournisseur de service téléphonique. Le serveur Survivable Branch Server est conçu pour les sites de succursale comptant entre 1 000 et 5 000 utilisateurs.

  - Une passerelle RTC et, éventuellement, un *serveur de médiation* . Pour plus d’informations sur cela et d’autres rôles de serveur, reportez-vous à [Rôles serveur dans Lync Server 2013](lync-server-2013-server-roles.md)

Une succursale dotée d’une liaison de réseau étendu (WAN) résistante vers un site central peut utiliser la troisième option, à savoir une passerelle RTC et éventuellement un serveur de médiation. Les sites de succursale équipés de liaisons plus vulnérables doivent utiliser un Survivable Branch Appliance ou un serveur Survivable Branch Server, qui garantissent la résistance nécessaire en cas de panne du réseau étendu (WAN). Par exemple, sur un site disposant d’un Survivable Branch Appliance ou un serveur Survivable Branch Server déployé, les utilisateurs peuvent quand même passer et recevoir des appels Voix Entreprise si le réseau étendu reliant le site de succurcale au site central ne fonctionne pas. Pour plus d’informations sur le Survivable Branch Appliance, le serveur Survivable Branch Server et la résistance, reportez-vous à [Planification de la résistance Voix Entreprise dans Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md) dans la documentation de planification.

## Topologies de site

Le déploiement doit comprendre au moins un site central et peut inclure aucun ou plusieurs sites de succursale. Chaque site de succursale est affilié à un site central. Le site central fournit au site de succursale les services Lync Server dont il ne dispose pas localement, comme les services de présence et de conférence.

Si vous disposez de plusieurs sites, vous pouvez regrouper par paires les pools frontaux sur différents sites pour activer les fonctionnalités de récupération d’urgence. Pour plus d’informations, reportez-vous à [Prise en charge de la haute disponibilité et de la récupération d’urgence dans Lync Server 2013](lync-server-2013-high-availability-and-disaster-recovery-support.md).

## Voir aussi

#### Concepts

[Rôles serveur dans Lync Server 2013](lync-server-2013-server-roles.md)  
[Prise en charge de la haute disponibilité et de la récupération d’urgence dans Lync Server 2013](lync-server-2013-high-availability-and-disaster-recovery-support.md)  

#### Autres ressources

[Planification de la résistance Voix Entreprise dans Lync Server 2013](lync-server-2013-planning-for-enterprise-voice-resiliency.md)

