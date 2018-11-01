---
title: Consultation du rapport de certificats dans Lync Server 2013
TOCTitle: Consultation du rapport de certificats dans Lync Server 2013
ms:assetid: 549cfc9b-3cc5-4483-a93c-fc0738c7f622
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg558651(v=OCS.15)
ms:contentKeyID: 53095423
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Consultation du rapport de certificats dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-21_

Le rapport de certificats contient tous les certificats requis dans le déploiement Lync Server 2013 recommandé. Les comptes de l’outil de planification pour les noms de sujet et les autres noms du sujet sont entrés. Le texte par défaut non modifié peut constituer un défi potentiel pour l’équipe qui est responsable de la demande et de l’émission des certificats. Les informations de certificat contiennent également des données sur l’emplacement à partir duquel le certificat peut généralement être émis. Si l’infrastructure ne dispose pas d’une PKI interne, tous les certificats peuvent être demandés par l’intermédiaire d’un fournisseur de certificats public. Les champs EKU et Affecter à du rapport sont très utiles pour connaître ce que doivent être l’objectif et l’emplacement de chaque certificat.

![Rapport d’administration de certificats](images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "Rapport d’administration de certificats")

Examinez et étudiez attentivement l’utilisation et l’objectif de chaque certificat dans le déploiement. En cas de doute sur le rôle d’un certificat, déterminez les éléments avec lesquels le serveur ou le service communique. Dans Lync Server 2013, les certificats ont deux objectifs principaux :

  - Mutual Transport Layer Security (MTLS) – Les ordinateurs impliqués dans la communication présentent chacun un certificat qui prouve leur identité à un autre ordinateur. On appelle cela l’authentification serveur. La communication ne peut pas commencer tant que chaque ordinateur n’a pas approuvé l’identité de l’autre ordinateur.

  - Chiffrement – Le chiffrement (Secure Sockets Layer ou SSL, et Transport Layer Security ou TLS) est un moyen très utile de sécuriser les communications, de garantir la confidentialité et de créer un système sûr de communication et de collaboration.

## Voir aussi

#### Autres ressources

[Consultation des rapports de l’administrateur dans Lync Server 2013](lync-server-2013-reviewing-the-administrator-reports.md)

