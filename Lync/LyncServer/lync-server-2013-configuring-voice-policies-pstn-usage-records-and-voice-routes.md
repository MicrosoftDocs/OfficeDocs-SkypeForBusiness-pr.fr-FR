---
title: "LS 2013 : Conf. des strat. de voix, des enr. ut. du RTC et it. des comm. voc."
TOCTitle: Configuration des stratégies de voix, des enregistrements d’utilisation du RTC et des itinéraires des communications vocales
ms:assetid: 1e5a15f9-6f42-4dc6-baaa-24daf54afc4d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398272(v=OCS.15)
ms:contentKeyID: 49296450
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des stratégies de voix, des enregistrements d’utilisation du RTC et des itinéraires des communications vocales dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-10-10_

Les stratégies de voix, les enregistrements d’utilisation RTC et les itinéraires des communications vocales sont étroitement liés. Pour configurer une stratégie de voix vous devez sélectionner des fonctionnalités d’appel, puis affecter des enregistrements d’utilisation RTC à la stratégie, qui spécifient les droits accordés aux utilisateurs et aux groupes auxquels la stratégie de voix est affectée. Les itinéraires des communications vocales reçoivent également des enregistrements d’utilisation RTC, qui permettent d’associer les itinéraires aux utilisateurs autorisés à les utiliser. En d’autres termes, les utilisateurs peuvent uniquement effectuer des appels qui utilisent des itinéraires pour lesquels ils disposent d’enregistrements d’utilisation RTC correspondants.

La procédure recommandée pour un nouveau déploiement de Voix Entreprise est de commencer à configurer une stratégie de voix qui comprend les enregistrements d’utilisation RTC appropriés, puis d’associer les itinéraires appropriés à chaque enregistrement d’utilisation RTC.

> [!NOTE]  
> Vous pouvez également créer des stratégies de voix avec l’étendue d’<em>utilisateur</em> et les affecter à des utilisateurs ou des groupes individuels.

Pour connaître en détail la marche à suivre pour effectuer chacune de ces tâches, reportez-vous aux procédures dans cette section.

## Dans cette section

  - [Configuration des stratégies de voix et des enregistrements d’utilisation RTC pour autoriser les fonctionnalités d’appel et les privilèges dans Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md)

  - [Affichage des enregistrements d’utilisation RTC dans Lync Server 2013](lync-server-2013-view-pstn-usage-records.md)

  - [Configuration des itinéraires de communications vocales pour les appels sortants dans Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md)

  - [Exportation et importation de la configuration du routage des communications vocales dans Lync Server 2013](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - [Publication des modifications en attente de la configuration du routage des communications vocales dans Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - [Test du routage des communications vocales dans Lync Server 2013](lync-server-2013-test-voice-routing.md)

