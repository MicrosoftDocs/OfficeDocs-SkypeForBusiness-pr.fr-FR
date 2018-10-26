---
title: Infrastructure à clé publique pour Lync Server 2013
TOCTitle: Infrastructure à clé publique pour Lync Server 2013
ms:assetid: 737c8a25-23e9-4494-ab76-5a7b729b44ca
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn481131(v=OCS.15)
ms:contentKeyID: 59679142
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Infrastructure à clé publique pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Microsoft Lync Server 2013 s’appuie sur les certificats pour l’authentification du serveur et pour établir une chaîne de confiance entre les clients et les serveurs et entre les différents rôles serveur. L’infrastructure à clé publique (PKI) de Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2, Windows Server 2008 et Windows Server 2003 fournit l’infrastructure permettant d’établir et de valider cette chaîne de confiance.

Les certificats sont des ID numériques. Ils identifient un serveur par son nom et indiquent ses propriétés. Afin de garantir que les informations d’un certificat sont valides, celui-ci doit être émis par une autorité de certification (CA) approuvée par les clients ou d’autres serveurs qui se connectent au serveur. Si le serveur se connecte uniquement avec d’autres clients et serveurs sur un réseau privé, la CA peut être une CA d’entreprise. Si le serveur interagit avec des entités en dehors du réseau privé, une CA publique peut être requise.

Même si les informations du certificat sont valides, il doit exister un moyen de vérifier que le serveur présentant le certificat est en fait celui représenté par le certificat. C’est ici que le PKI de Windows entre en jeu.

Chaque certificat est lié à une clé publique. Le serveur nommé sur le certificat contient une clé privée correspondante que lui seul connaît. Un client ou serveur se connectant utilise la clé publique pour chiffrer une information aléatoire et l’envoie au serveur. Si le serveur déchiffre l’information et la retourne sous forme de texte simple, l’entité se connectant peut ainsi être sûre que le serveur contient la clé privée du certificat et qu’il s’agit donc du serveur nommé sur le certificat.

> [!NOTE]  
> Toutes les CA publiques ne respectent pas les exigences des certificats Lync Server 2013. Nous vous conseillons de vous reporter à la liste des CA publiques approuvées pour vos besoins de certificats publics. Pour plus d’informations, voir Partenaires de certificat de communications unifiées à l’adresse : <a href="http://go.microsoft.com/fwlink/p/?linkid=140898">http://go.microsoft.com/fwlink/p/?LinkId=140898</a>.

## Points de distribution de liste de révocation de certificats

Lync Server 2013 exige que tous les certificats de serveur contiennent un ou plusieurs points de distribution de liste de révocation de certificats (CRL). Les points de distribution CRL (CDP) sont des emplacements à partir desquels les CRL peuvent être téléchargés en vue de vérifier que le certificat n’a pas été révoqué depuis son émission et qu’il est toujours dans sa période de validité. Un point de distribution CRL est indiqué dans les propriétés du certificat sous forme d’URL, et il s’agit généralement d’une adresse HTTP sécurisée.

## Utilisation améliorée de la clé

Lync Server 2013 exige que tous les certificats de serveur prennent en charge l’utilisation améliorée de la clé (EKU) pour l’authentification du serveur. La configuration du champ EKU pour l’authentification du serveur signifie que le certificat est valide pour l’authentification des serveurs. Cette EKU est essentielle pour MTLS. Il est possible d’avoir plusieurs entrées dans l’EKU, ce qui permet au certificat d’avoir plusieurs rôles.

> [!NOTE]  
> L’EKU d’authentification client est requise pour les connexions MTLS sortantes de Live Communications Server 2003 et Live Communications Server 2005, mais elle n’est plus requise. Toutefois, cette EKU doit être présente sur les serveurs Edge qui se connectent à AOL par le biais d’une solution PIC (Public IM Connectivity).
