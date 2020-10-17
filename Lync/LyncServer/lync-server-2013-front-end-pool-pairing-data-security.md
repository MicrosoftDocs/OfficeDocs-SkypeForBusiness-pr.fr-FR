---
title: 'Lync Server 2013 : sécurité des données d’appariement de pools frontaux'
description: 'Lync Server 2013 : sécurité des données d’appariement de pools frontaux.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Front End pool pairing data security
ms:assetid: edb852b8-ea86-4948-b756-60fe6ee876d2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721930(v=OCS.15)
ms:contentKeyID: 49733865
ms.date: 10/07/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 32a2ce72752819392429c8407649e663494f1daf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567130"
---
# <a name="front-end-pool-pairing-data-security-in-lync-server-2013"></a>Sécurité des données de jumelage des pools frontaux dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-10-07_

Le service de sauvegarde est un mécanisme de réplication des données introduit dans Lync Server 2013 qui transfère les données utilisateur et le contenu de conférence entre deux pools frontaux couplés en continu entre deux centres de données à des fins de récupération d’urgence. Les données utilisateur contiennent les URI SIP de l’utilisateur, ainsi que les listes de contacts et les paramètres. Le contenu des conférences inclut les téléchargements de Microsoft PowerPoint 2010, ainsi que les tableaux blancs utilisés dans les conférences. À partir du pool source, les données utilisateur et le contenu de conférence sont exportés à partir du stockage local, zippé, transféré vers le pool cible, où il est décompressé et importé dans le stockage local. Le service de sauvegarde suppose que la liaison de communication entre les deux centres de données se trouve dans le réseau d’entreprise protégé d’Internet. Il ne chiffre pas les données transférées entre les deux centres de données, et n’est pas encapsulé de manière native dans un protocole sécurisé, tel que HTTPs. Par conséquent, l’attaque de l’intercepteur du personnel interne au sein du réseau d’entreprise est possible.

<div>

## <a name="evaluating-security-risks"></a>Évaluation des risques de sécurité

Toute entreprise qui déploie Lync Server 2013 sur plusieurs centres de données et qui utilise la fonctionnalité de récupération d’urgence doit s’assurer que le trafic du centre de données croisée est protégé par son intranet d’entreprise. Les entreprises qui se soucient de la protection contre les attaques internes doivent sécuriser les liens de communication entre les centres de données.

L’hypothèse que les centres de données d’une entreprise sont protégés derrière l’intranet d’entreprise est standard. Il existe de nombreux autres types de données sensibles d’entreprise transférées entre ces centres de données. L’infrastructure informatique de l’entreprise est un risque catastrophique si ces liens entre les centres de données ne sont pas protégés.

Bien que le risque d’attaques de l’intercepteur dans le réseau d’entreprise existe, il est relativement important par rapport à l’exposition du trafic sur Internet. Plus précisément, les données utilisateur exposées par le service de sauvegarde (comme les URI SIP) sont généralement accessibles à tous les employés au sein de l’entreprise par le biais d’autres moyens tels que le carnet d’adresses global d’Exchange ou d’autres logiciels d’annuaire. Par conséquent, la sécurisation du réseau étendu doit être activée entre les deux centres de données lorsque le service de sauvegarde est utilisé pour copier les données entre les deux pools couplés.

</div>

<div>

## <a name="mitigating-security-risks"></a>Atténuation des risques de sécurité

Il existe de nombreuses façons d’améliorer la sécurité du trafic du service de sauvegarde, qu’il s’agisse de restreindre l’accès aux centres de données pour sécuriser le transport WAN entre les deux centres de données. Dans la plupart des cas, les entreprises déployant Lync Server 2013 peuvent avoir déjà l’infrastructure de sécurité requise en place. Pour les entreprises qui cherchent des conseils, Microsoft propose une solution comme exemple de création d’une infrastructure informatique sécurisée. Toutefois, cela ne signifie pas qu’il s’agit de la seule solution, ni qu’il s’agit de la solution par défaut pour Lync Server. Nous recommandons aux clients d’entreprise de choisir la solution qui répond à leurs besoins spécifiques en fonction de leurs besoins et de l’infrastructure de sécurité informatique. L’exemple de solution Microsoft utilise IPSec et la stratégie de groupe pour l’isolation de serveur et de domaine. Pour plus d’informations, reportez-vous à [https://go.microsoft.com/fwlink/p/?LinkId=268544](https://go.microsoft.com/fwlink/p/?linkid=268544) . Pour obtenir des questions et des commentaires, contactez secwish@microsoft.com.

Une autre solution possible consiste à utiliser IPSec uniquement pour sécuriser les données envoyées par le service de sauvegarde lui-même. Si vous choisissez cette méthode, vous devez configurer les règles IPSec pour le protocole SMB pour les serveurs suivants, où le pool A et le pool B sont deux pools frontaux couplés.

  - Service SMB (TCP/445) de chaque serveur frontal dans le pool A vers le magasin de fichiers utilisé par le pool B.

  - Service SMB (TCP/445) de chaque serveur frontal dans le pool B vers le magasin de fichiers utilisé par le pool A.

<div>


> [!WARNING]  
> IPsec n’est pas destiné à remplacer la sécurité au niveau de l’application, comme SSL/TLS. L’un des avantages de l’utilisation d’IPsec est qu’elle permet de sécuriser le trafic réseau pour les applications existantes sans qu’il soit nécessaire de les modifier. Les entreprises qui souhaitent sécuriser le transport entre les deux centres de données doivent consulter leurs fournisseurs de matériel réseau respectifs sur les moyens de configurer des connexions WAN sécurisées à l’aide de l’équipement du fournisseur.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

