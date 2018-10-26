---
title: 'Lync Server 2013 : Jonction M:N'
TOCTitle: Jonction M:N
ms:assetid: dc4c5d66-297c-48a5-91b9-b9b8ce44a6e0
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398971(v=OCS.15)
ms:contentKeyID: 49299067
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Jonction M:N dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-01_

Lync Server 2013 offre une flexibilité accrue dans la définition d’une jonction à des fins de routage des appels par rapport aux versions précédentes. Une jonction est une association logique entre un serveur de médiation et un numéro de port d’écoute avec une passerelle et un numéro de port d’écoute. Cela a plusieurs implications : un serveur de médiation peut avoir plusieurs jonctions vers la même passerelle ; un serveur de médiation peut avoir plusieurs jonctions vers différentes passerelles ; et inversement, une passerelle peut avoir plusieurs jonctions vers différents serveurs de médiation.

Une jonction racine doit toujours être créée quand une passerelle est ajoutée à la topologie Lync à l’aide du Générateur de topologie. Le nombre de passerelles pouvant être gérées par un serveur de médiation donné dépend de la capacité de traitement du serveur aux heures de pointe. Si vous déployez un serveur de médiation sur du matériel qui excède la configuration matérielle minimale requise pour Lync Server 2013 (comme décrit dans la section «  [Matériel pris en charge pour Lync Server 2013](lync-server-2013-supported-hardware.md) » de la documentation sur la capacité de prise en charge), le nombre d’appels actifs pouvant être gérés par un serveur de médiation autonome est d’environ 1 000 appels. Lorsqu’il est déployé sur du matériel conforme à ces spécifications, le serveur de médiation est censé effectuer le transcodage, mais il continue d’acheminer les appels vers plusieurs passerelles, même si elles ne prennent pas en charge la déviation du trafic multimédia.

Lorsque vous définissez un itinéraire téléphonique, vous spécifiez les jonctions, mais pas les serveurs de médiation, qui lui sont associées. Vous devez utiliser le Générateur de topologie pour associer les jonctions aux serveurs de médiation. En d’autres termes, le routage détermine quelle jonction utiliser pour un appel, puis la signalisation pour cette appel est envoyée au serveur de médiation associé à cette jonction.

Le serveur de médiation peut être déployé en tant que pool qui peut être colocalisé avec un pool de serveurs frontaux ou déployé en tant que pool autonome. Lorsqu’un serveur de médiation est colocalisé avec un pool de serveurs frontaux, le pool peut contenir 12 serveurs au plus (taille maximale du pool de serveurs d’inscription). Ensemble, ces nouvelles fonctionnalités augmentent la fiabilité et la facilité de déploiement d’un serveurs de médiation, mais elles doivent être associées à d’autres fonctionnalités dans les entités homologues suivantes :

  - **Passerelle RTC.** Une passerelle qualifiée Lync Server 2013 doit implémenter l’équilibrage de la charge DNS, ce qui permet à une passerelle RTC qualifiée de jouer le rôle de programme d’équilibrage de charge pour un pool de serveurs de médiation, et ainsi d’équilibrer la charge des appels dans le pool.

  - **Contrôleur de frontière de session.** Pour une jonction SIP, l’entité homologue est un contrôleur de frontière de session (SBC) chez un fournisseur de services de téléphonie Internet. Dans le sens pool de serveurs de médiation-Contrôleur SBC, le contrôleur SBC peut recevoir des connexions provenant de tout serveur de médiation du pool. Dans le sens Contrôleur SBC-Pool, le trafic peut être acheminé vers n’importe quel serveur de médiation du pool. L’équilibrage de la charge DNS permet d’y parvenir si le fournisseur de services et le contrôleur SBC le prennent en charge. Il est également possible de donner au fournisseur de services les adresses IP de tous les serveurs de médiation du pool. Il les configure alors dans son contrôleur SBC en tant que jonction SIP distincte pour chaque serveur de médiation. Le fournisseur de services gère ensuite l’équilibrage de charge pour ses propres serveurs. Tous les fournisseurs de services ou contrôleurs SBC ne prennent pas en charge ces fonctionnalités. Et certains fournisseurs de services font payer cette fonctionnalité. Chaque jonction SIP vers le contrôleur SBC requiert généralement le paiement d’une redevance mensuelle.

  - **IP-PBX.**Dans le sens pool de serveurs de médiation-Terminaison SIP IP-PBX, le système IP-PBX peut recevoir des connexions provenant de n’importe quel serveur de médiation du pool. Dans le sens IP-PBX-Pool, le trafic peut être acheminé vers n’importe quel serveur de médiation du pool. Comme la plupart des systèmes IP-PBX ne prennent pas en charge l’équilibrage de charge DNS, il est conseillé de définir des connexions SIP directes individuelles du système IP-PBX vers chaque serveur de médiation du pool. Le système IP-PBX gère ensuite son propre équilibrage de charge en répartissant le trafic dans le groupe de jonctions, supposé avoir un ensemble cohérent de règles de routage sur le système IP-PBX. Avant de décider si un cluster de serveur de médiation peut interagir correctement avec un système IP-PBX, vous devez déterminer si un système IP-PBX donné prend en charge ce concept de groupe de jonctions et comment il s’articule avec l’architecture de redondance et de clustering du système IP-PBX.

Un pool de serveurs de médiation doit disposer d’une vue uniforme de la passerelle homologue avec laquelle il interagit. Cela signifie que tous les membres du pool accèdent à la même définition de passerelle homologue à partir du magasin de configurations et qu’ils ont tous autant de chances d’interagir avec elle pour les appels sortants. Par conséquent, il n’est pas possible de segmenter le pool pour que quelques serveurs de médiation communiquent avec certains homologues de passerelles uniquement pour les appels sortants. S’il est nécessaire de procéder à cette segmentation, vous devez utiliser un pool distinct de serveurs de médiation. Ce serait le cas, par exemple, si les fonctionnalités associées dans les passerelles RTC, jonctions SIP ou systèmes IP-PBX pour interagir avec un pool n’étaient pas présentes (voir plus haut dans cette rubrique).

Une passerelle RTC particulière, ou un système IP-PBX ou un homologue de jonction SIP particulier peut acheminer des appels vers plusieurs serveurs de médiation ou jonctions. Le nombre de passerelles pouvant être contrôlées par un pool donné de serveurs de médiation dépend du nombre d’appels qui utilisent la déviation du trafic multimédia. Si de nombreux appels utilisent la déviation du trafic multimédia, un serveur de médiation du pool peut gérer bien d’autres appels, car seul le traitement de couche de signalisation est nécessaire.

