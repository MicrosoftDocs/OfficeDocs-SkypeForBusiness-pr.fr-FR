---
title: "Compat. de Lync Server 2013 avec la résist. de sites métrop. Lync Server 2010"
TOCTitle: Résistance de sites métropolitains Lync Server 2010
ms:assetid: 18673ff6-b664-4a57-a89b-cbda8b129e6a
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ204715(v=OCS.15)
ms:contentKeyID: 49296386
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Résistance de sites métropolitains Lync Server 2010

 

_**Dernière rubrique modifiée :** 2014-03-19_

La solution de résistance de sites métropolitains prise en charge pour Lync Server 2010 n’est pas prise en charge pour Lync Server 2013. Cette solution nécessitait qu’un seul pool frontal couvre deux centres de données au sein de la même zone métropolitaine.

La solution de résistance de sites métropolitains a été conçue pour la récupération après la perte d’un centre de données complet. Lorsque votre pool couvre deux centres de données, vous placez généralement la moitié de vos pools frontaux dans un centre de données et l’autre moitié dans le second. Si vous perdez un centre de données complet, vous perdez la moitié de vos serveurs frontaux. Cela peut entraîner des problèmes avec le nouveau modèle de systèmes distribués pour les pools frontaux dans Lync Server 2013. Pour plus d’informations, reportez-vous à [Topologies et composant utilisés pour les serveurs frontaux, la messagerie instantanée et la présence dans Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).

