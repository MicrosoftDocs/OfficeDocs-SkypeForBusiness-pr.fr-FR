---
title: 'Lync Server 2013 : réduction des messages instantanés non sollicités'
TOCTitle: Réduction des messages instantanés non sollicités pour Lync Server 2013
ms:assetid: d2998708-e699-4465-a918-e1d9ea4c49c3
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn518335(v=OCS.15)
ms:contentKeyID: 60484532
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Réduction des messages instantanés non sollicités pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-12-05_

L’application Filtre de messagerie instantanée intelligent permet de protéger votre déploiement Microsoft Lync Server 2013 contre les virus les plus fréquents avec une dégradation minimale pour l’expérience utilisateur. L’application Filtre de messagerie instantanée intelligent possède les avantages suivants :

  - Filtrage d’URL amélioré

  - Filtrage des transferts de fichier amélioré

Utilisez le Filtre de message instantané intelligent pour configurer les filtres de façon à bloquer les messages instantanés non sollicités ou potentiellement dangereux en provenance de points de terminaison externes au pare-feu d’entreprise. Vous configurez des filtres en spécifiant les critères à utiliser pour déterminer ce qui doit être bloqué, comme les messages instantanés contenant des liens hypertexte et les fichiers avec des extensions spécifiques.

Avant de déployer l’application Filtre de messagerie instantanée intelligent, vous devez comprendre comment les options de filtrage sont appliquées lorsque les messages sont acheminés d’un serveur Lync Server 2013 vers un autre. L’application de ces options de filtrage est toujours effectué de la même manière, que les serveurs soient situés à l’intérieur d’une même organisation ou qu’ils soient disséminés dans plusieurs organisations. Cette cohérence concerne la façon dont les notices personnalisées et les textes d’avertissement sont insérés dans des messages et envoyés sur les serveurs.

L’option de filtrage recommandée consiste à autoriser les messages instantanés avec des liens hypertexte, mais implique que l’application Filtre de messagerie instantanée intelligent désactive le lien en insérant un trait de soulignement avant le lien. Si vous sélectionnez cette option, vous disposez d’une option supplémentaire qui permet de rédiger une notice à l’attention des utilisateurs, qui s’affiche au début de chaque message instantané contenant un lien hypertexte.

La deuxième option de filtrage autorise les messages instantanés avec des liens hypertexte non modifiés. Si vous sélectionnez cette option, vous disposez d’une option supplémentaire (recommandée) permettant de rédiger un avertissement à l’attention des utilisateurs, inséré dans chaque message.

La troisième option bloque tous les messages instantanés contenant des liens hypertexte. Si vous sélectionnez cette option, le serveur envoie un avertissement à l’utilisateur. C’est à vous de rédiger cet avertissement.

