---
title: Meilleures pratiques pour votre infrastructure de base dans Lync Server 2013
TOCTitle: Meilleures pratiques pour votre infrastructure de base dans Lync Server 2013
ms:assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn518328(v=OCS.15)
ms:contentKeyID: 60484453
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Meilleures pratiques pour votre infrastructure de base dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Vous avez probablement déjà pris des mesures pour intégrer la tolérance de pannes dans votre système, en utilisant des pratiques telles que la garantie de la redondance matérielle, la prévention de la perte d'alimentation, l'installation régulière des mises à jour, l'établissement des mesures de sécurité antivirus et la surveillance de l'activité du serveur. Ces pratiques bénéficient non seulement à votre infrastructure Microsoft Lync Server 2013, mais aussi à l'ensemble de votre réseau. Si vous n'avez pas implémenté ces pratiques, nous vous recommandons de le faire avant de déployer Lync Server 2013.

Pour mieux protéger vos serveurs lors du déploiement de Lync Server 2013 contre tout dommage volontaire ou accidentel pouvant entraîner une interruption de service, prenez les précautions suivantes :

  - Gardez vos serveurs à jour avec les mises à jour de sécurité. En vous abonnant au service de notification de sécurité de Microsoft, vous recevez la notification immédiate des bulletins de sécurité pour les produits Microsoft. Pour vous abonner, rendez-vous sur le site Web des notifications de sécurité techniques de Microsoft à l'adresse : [http://go.microsoft.com/fwlink/p/?LinkId=145202](http://go.microsoft.com/fwlink/p/?linkid=145202).

  - Assurez-vous que les droits d'accès sont configurés correctement.

  - Conservez vos serveurs dans un environnement physique qui empêche l'accès non autorisé. Assurez-vous que le logiciel antivirus adéquat est installé sur tous vos serveurs. Maintenez le logiciel à jour avec les derniers fichiers de signatures de virus. Utilisez la fonction de mise à jour automatique de votre application antivirus pour maintenir à jour les signatures de virus.

  - Nous vous recommandons de désactiver les services du système d'exploitation Windows Server qui ne sont pas nécessaires sur les ordinateurs sur lesquels vous installez Lync Server 2013.

  - Chiffrez les systèmes d'exploitation et les lecteurs de disques où les données sont stockées à l'aide d'un système de chiffrement de volume complet, sauf si vous pouvez garantir un contrôle constant et total des serveurs, l'isolement physique complet et la désaffectation adéquate et sûre des disques remplacés ou défaillants.

  - Désactivez tous les ports DMA (Direct Memory Access) externes du serveur, sauf si vous pouvez garantir un contrôle très strict de l'accès physique aux serveurs. Les attaques basées sur DMA, qui peuvent être lancées assez facilement, risquent d'exposer des informations très sensibles, telles que les clés de chiffrement privées.

