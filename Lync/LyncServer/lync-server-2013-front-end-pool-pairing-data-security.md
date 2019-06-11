---
title: 'Lync Server 2013 : sécurité des données d’appariement de pools frontaux'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Front End pool pairing data security
ms:assetid: edb852b8-ea86-4948-b756-60fe6ee876d2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721930(v=OCS.15)
ms:contentKeyID: 49733865
ms.date: 10/07/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db1a408aecedc14162271d5def1adc2bcebdfd82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831141"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="front-end-pool-pairing-data-security-in-lync-server-2013"></a>Sécurité des données d’appariement de pools frontaux dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-10-07_

Le service de sauvegarde est un mécanisme de réplication des données introduit dans Lync Server 2013, qui permet de transférer les données utilisateur et le contenu de la conférence entre deux listes frontales couplées en continu sur deux centres de données à des fins de reprise après sinistre. Les données utilisateur contiennent les URI SIP de l’utilisateur ainsi que les listes de contacts et les paramètres. Le contenu de la Conférence inclut les téléchargements Microsoft PowerPoint 2010 ainsi que les tableaux blancs utilisés en conférences. À partir de la liste source, les données utilisateur et le contenu de la Conférence sont exportés à partir du stockage local, compressé et transférés vers le pool cible, où il est décompressé et importé dans le stockage local. Le service de sauvegarde part du principe que le lien de communication entre les deux centres de données est à l’intérieur du réseau d’entreprise qui est protégé d’Internet. Le chiffrement des données transférées entre les deux centres de données n’est pas crypté en natif au sein d’un protocole sécurisé tel que HTTPs. Par conséquent, il est possible d’attaquer par le biais d’une attaque par le biais du milieu interne au sein du réseau d’entreprise.

<div>

## <a name="evaluating-security-risks"></a>Évaluation des risques en matière de sécurité

Toute entreprise qui déploie Lync Server 2013 sur plusieurs centres de données et utilise la fonctionnalité de reprise après sinistre doit garantir que le trafic du centre de données est protégé par l’intranet de l’entreprise. Les entreprises qui se soucient de la protection interne contre les attaques doivent sécuriser les liens entre les centres de données.

L’hypothèse selon laquelle les centres de données d’une entreprise sont protégés au-delà de l’intranet de l’entreprise est standard. Il existe de nombreux autres types de données sensibles d’entreprise transférées entre ces centres de données. L’infrastructure informatique de l’entreprise est un risque catastrophique si ces liens entre les centres de données ne sont pas protégés.

Si le risque d’attaques de l’intercepteur (« man-in-the-middle ») sur le réseau d’entreprise existe, il est relativement contrôlé en comparaison de l’exposition du trafic sur Internet. Plus précisément, les données utilisateur exposées par le service de sauvegarde (par exemple, les URI SIP) sont généralement disponibles pour tous les employés au sein de l’entreprise via d’autres moyens tels que le carnet d’adresses global d’Exchange ou d’autres logiciels d’annuaire. Par conséquent, le focus doit être placé sur la sécurité du réseau étendu (WAN) entre les deux centres de données lorsque le service de sauvegarde est utilisé pour copier des données entre les deux pools couplés.

</div>

<div>

## <a name="mitigating-security-risks"></a>Réduction des risques liés à la sécurité

Il existe de nombreuses façons d’améliorer la protection de la sécurité du trafic du service de sauvegarde, qu’il s’agisse de limiter l’accès aux centres de données pour sécuriser le transport WAN entre les deux centres de données. Dans la plupart des cas, les entreprises qui déploient Lync Server 2013 peuvent avoir déjà l’infrastructure de sécurité requise en vigueur. Pour les entreprises recherchant des recommandations, Microsoft fournit une solution comme exemple de création d’une infrastructure informatique sécurisée. Toutefois, cela ne signifie pas qu’il s’agit de la seule solution et qu’elle n’implique pas qu’il s’agit de la solution préférée pour Lync Server. Nous recommandons aux clients d’entreprise de choisir une solution adaptée à leurs besoins spécifiques en fonction de leur infrastructure de sécurité informatique et de leurs besoins. L’exemple de solution Microsoft utilise IPSec et la stratégie de groupe pour l’isolement du serveur et du domaine. Pour plus d’informations [http://go.microsoft.com/fwlink/p/?LinkId=268544](http://go.microsoft.com/fwlink/p/?linkid=268544), reportez-vous à. Pour des questions et des commentaires, contactez secwish@microsoft.com.

Une autre solution possible consiste à utiliser IPSec simplement pour sécuriser les données envoyées par le service de sauvegarde proprement dit. Si vous choisissez cette méthode, vous devez configurer les règles IPSec du protocole SMB pour les serveurs ci-dessous, où le pool A et le pool B sont deux pools frontaux associés.

  - Service SMB (TCP/445) de chaque serveur frontal dans le pool A vers le magasin de fichiers utilisé par le pool B.

  - Service SMB (TCP/445) de chaque serveur frontal dans le pool B vers le magasin de fichiers utilisé par le pool A.

<div>


> [!WARNING]  
> IPsec n’est pas destiné à remplacer la sécurité au niveau de l’application, comme SSL/TLS. L’intérêt d’utiliser IPsec est qu’il peut assurer la sécurité du trafic réseau pour les applications existantes sans avoir à les modifier. Les entreprises qui veulent simplement sécuriser le transport entre les deux centres de données doivent s’adresser à leurs fournisseurs de matériel réseau respectifs pour savoir comment configurer des connexions de réseau étendu (WAN) sécurisées avec leur matériel.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

