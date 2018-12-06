---
title: 'Lync Server 2013 : sécurité des données d’appariement de pools frontaux'
TOCTitle: Sécurité des données d’appariement de pools frontaux
ms:assetid: edb852b8-ea86-4948-b756-60fe6ee876d2
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ721930(v=OCS.15)
ms:contentKeyID: 49891599
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Sécurité des données d’appariement de pools frontaux dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Le service de sauvegarde est un mécanisme de réplication de données introduit dans Lync Server 2013 qui transfère les données utilisateur et le contenu de conférence entre deux pools de serveurs frontaux couplés de manière continue sur deux centres de données à des fins de récupération d’urgence. Les données utilisateur contiennent des URI SIP d’utilisateur, ainsi que des paramètres et listes de contacts. Le contenu de conférence inclut des téléchargements Microsoft PowerPoint 2010, ainsi que les tableaux blancs utilisés lors des conférences. Dans le pool source, les données utilisateur et le contenu de conférence sont exportés à partir du stockage local, compressés, transférés au pool cible, où ils sont décompressés, et importés vers le stockage local. Le service de sauvegarde part du principe que le lien de communication entre les deux centres de données est à l’intérieur du réseau d’entreprise qui est protégé d’Internet. Il ne chiffre pas les données transférées entre les deux centres de données, et n’est pas non plus encapsulé de manière native dans un protocole sécurisé, tel que HTTPS. Ainsi, une attaque de l’intercepteur (« man-in-the-middle ») du personnel interne au sein du réseau d’entreprise est possible.

## Évaluation des risques de sécurité

Toute entreprise qui déploie Lync Server 2013 sur plusieurs centres de données et qui utilise la fonctionnalité de récupération d’urgence doit s’assurer que le trafic entre centres de données est protégé par son Intranet. Les entreprises qui se soucient de la protection contre les attaques internes doivent sécuriser les liens de communication entre les centres de données.

Il est généralement supposé que les centres de données d’une entreprise sont protégés derrière son Intranet. Il existe de nombreux autres types de données professionnelles confidentielles transférées entre ces centres de données. L’infrastructure informatique de l’entreprise court des risques considérables si ces liens entre centres de données ne sont pas protégés.

Si le risque d’attaques de l’intercepteur (« man-in-the-middle ») sur le réseau d’entreprise existe, il est relativement contrôlé en comparaison de l’exposition du trafic sur Internet. Plus précisément, les données utilisateur exposées par le service de sauvegarde (tels les URI SIP) sont généralement disponibles pour tous les employés de l’entreprise via d’autres moyens tels que le carnet d’adresses global d’Exchange ou autre logiciel de répertoire. L’attention doit donc être portée sur la sécurisation du réseau étendu (WAN) entre les deux centres de données lorsque le service de sauvegarde est utilisé pour copier les données entre les deux pools couplés.

## Réduction des risques de sécurité

Il existe différentes façons d’améliorer la protection de la sécurité du trafic du service de sauvegarde, qui vont de la restriction de l’accès aux centres de données à la sécurisation du transport de réseau étendu (WAN) entre deux centres de données. Dans la plupart des cas, l’infrastructure de sécurité requise est déjà mise en place dans les entreprises déployant Lync Server 2013. Pour celles qui recherchent de l’aide, Microsoft fournit un exemple de procédure d’élaboration d’une infrastructure informatique sécurisée. Cependant, cela ne signifie pas qu’il s’agit de la seule solution, ni de la solution privilégiée pour Lync Server. Nous recommandons aux clients entreprises de choisir la solution adaptée à leurs besoins spécifiques, en fonction de leur infrastructure et de leurs exigences de sécurité informatique. La solution Microsoft de l’exemple utilise le protocole IPSec et la stratégie de groupe pour l’isolation des serveurs et des domaines. Pour plus d’informations, reportez-vous à la section [http://go.microsoft.com/fwlink/p/?LinkId=268544](http://go.microsoft.com/fwlink/p/?linkid=268544). Si vous avez des questions et des commentaires, contactez secwish@microsoft.com.

Une autre solution possible consiste à utiliser IPSec simplement pour sécuriser les données envoyées par le service de sauvegarde proprement dit. Si vous choisissez cette méthode, vous devez configurer les règles IPSec du protocole SMB pour les serveurs ci-dessous, où le pool A et le pool B sont deux pools de serveurs frontaux appariés.

  - Service SMB (TCP/445) de chaque serveur frontal dans le pool A vers le magasin de fichiers utilisé par le pool B.

  - Service SMB (TCP/445) de chaque serveur frontal dans le pool B vers le magasin de fichiers utilisé par le pool A.

> [!WARNING]  
> IPsec n’est pas destiné à remplacer la sécurité au niveau de l’application, comme SSL/TLS. L’intérêt d’utiliser IPsec est qu’il peut assurer la sécurité du trafic réseau pour les applications existantes sans avoir à les modifier. Les entreprises qui veulent simplement sécuriser le transport entre les deux centres de données doivent s’adresser à leurs fournisseurs de matériel réseau respectifs pour savoir comment configurer des connexions de réseau étendu (WAN) sécurisées avec leur matériel.
