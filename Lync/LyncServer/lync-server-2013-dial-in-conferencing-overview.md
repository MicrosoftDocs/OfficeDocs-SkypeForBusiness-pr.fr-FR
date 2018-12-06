---
title: Vue d’ensemble de la conférence rendez-vous dans Lync Server 2013
TOCTitle: Vue d’ensemble de la conférence rendez-vous dans Lync Server 2013
ms:assetid: 6e581cef-960a-4730-8b22-91b2129d34e3
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398524(v=OCS.15)
ms:contentKeyID: 49297576
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Vue d’ensemble de la conférence rendez-vous dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-30_

Si des utilisateurs de votre organisation doivent participer à des conférences Lync Server 2013 locales lorsqu’ils sont en déplacement ou ne disposent pas d’un accès à un ordinateur, vous pouvez déployer la conférence rendez-vous afin qu’ils puissent joindre la conférence à l’aide d’un téléphone de réseau téléphonique commuté (RTC).

La conférence rendez-vous est une fonctionnalité facultative que vous pouvez configurer lorsque vous déployez la conférence Lync Server 2013. Même si la conférence rendez-vous utilise certains des mêmes composants Lync Server 2013 que Voix Entreprise, vous pouvez la déployer même si vous ne déployez pas Voix Entreprise.

> [!NOTE]  
> Si vous déployez la conférence rendez-vous, vous devez la déployer dans chaque pool sur lequel vous déployez la conférence Lync Server 2013. Il n’est pas nécessaire d’attribuer des numéros d’accès à chaque pool, mais vous devez déployer la fonctionnalité Conférence rendez-vous dans chaque pool. Cette condition préalable prend en charge la fonctionnalité d’enregistrement du nom lorsqu’un utilisateur appelle un numéro d’accès depuis un pool pour joindre une conférence Lync Server 2013 dans un autre pool.

Les conférences doivent être activées pour l’accès par modem dans la stratégie de réunion. Par défaut, les conférences activées pour les accès par modem comportent les informations suivantes dans l’invitation à la conférence :

  - Un ID numérique de conférence qui identifie la conférence.

  - Un ou plusieurs numéros d’accès RTC.

  - Un lien vers une page Paramètres de conférence rendez-vous qui contient la liste complète des numéros d’accès avec leurs langues associées, un emplacement pour créer, réinitialiser ou débloquer les codes confidentiels, et d’autres informations telles que les contrôles DTMF (numérotation en fréquences vocales).

La fonction de conférence rendez-vous est prise en charge pour les utilisateurs d’entreprise et les utilisateurs anonymes. Les utilisateurs d’entreprise disposent d’informations d’identification des services de domaine Active Directory et de comptes Lync Server 2013 dans leur organisation. Les utilisateurs anonymes ne disposent pas d’informations d’identification dans votre organisation. Dans le contexte d’une conférence rendez-vous, un utilisateur d’une organisation d’un partenaire fédéré qui utilise le RTC pour se connecter à une conférence est considéré comme un utilisateur anonyme. Pour la conférence rendez-vous, contrairement aux autres contextes, les utilisateurs fédérés ne sont pas authentifiés.

Les utilisateurs d’entreprise ou les organisateurs de conférence qui joignent une conférence activée pour l’accès par modem composent un des numéros d’accès à la conférence, puis sont invités à entrer l’ID de conférence. Si un organisateur n’a pas encore rejoint la réunion, les utilisateurs peuvent entrer leur extension de communications unifiées (ou leur numéro de téléphone complet) et leur code confidentiel, ou attendre d’être admis par l’organisateur. L’organisateur de la réunion peut joindre la réunion en tant que tel en entrant seulement son code confidentiel. Le serveur frontal utilise l’association de l’extension du numéro de téléphone complet et du code confidentiel pour mapper de manière unique les utilisateurs d’entreprise à leurs informations d’identification Active Directory. Ils sont ainsi authentifiés et identifiés à l’aide de leur nom dans la conférence. Ils peuvent également adopter un rôle de conférence prédéfini par l’organisateur.

> [!NOTE]  
> Les utilisateurs d’entreprise qui se joignent à la conférence à partir d’un téléphone IP de bureau, de Lync Server 2013 ou de Intendant Lync 2010 ne sont pas invités à indiquer leur numéro de téléphone car ils sont déjà authentifiés.

Les utilisateurs anonymes qui souhaitent se joindre à une conférence composent un des numéros d’accès à la conférence, puis sont invités à entrer l’ID de conférence. Les utilisateurs anonymes non identifiés sont également invités à enregistrer leur nom. Le nom enregistré identifie les utilisateurs non authentifiés au sein de la conférence. Les utilisateurs anonymes ne sont pas admis à la conférence tant qu’au moins un organisateur ou utilisateur authentifié ne s’y est pas joint. Aucun rôle prédéfini ne peut leur être attribué.

> [!NOTE]  
> Les utilisateurs d’entreprise qui décident de ne pas entrer leur numéro de téléphone ni leur code confidentiel ne sont pas considérés comme authentifiés. Ils sont invités à enregistrer leur nom et traités comme des utilisateurs anonymes dans la conférence.

Au moment de la planification, l’organisateur de la réunion peut décider de restreindre l’accès à la réunion en la fermant ou en la verrouillant. Dans ce cas, les utilisateurs appelants sont invités à s’authentifier. S’ils échouent ou décident de ne pas s’authentifier, ils sont transférés vers la salle d’attente. Ils patientent dans la salle d’attente jusqu’à ce qu’un responsable les valide ou les refuse, ou ils sont déconnectés une fois leur délai d’expiration écoulé. Les utilisateurs appelants entendent de la musique s’ils attendent d’être admis à la conférence. Une fois admis dans une conférence, les utilisateurs d’appels entrants peuvent participer à la portion audio de la conférence et exécuter des commandes de numérotation en fréquences vocales (DTMF) à partir du clavier du téléphone. Les responsables de conférences rendez-vous peuvent exécuter des commandes DTMF pour admettre des personnes de la salle d’attente, activer ou désactiver le micro des participants, verrouiller ou déverrouiller la conférence et activer ou désactiver les annonces d’entrée et de sortie. Les organisateurs peuvent également utiliser une commande DTMF pour admettre toutes les personnes de la salle d’attente, ce qui a pour effet de modifier les autorisations de la réunion en autorisant toute personne qui rejoint ultérieurement la réunion. Tous les participants d’appels entrants peuvent exécuter des commandes DTMF pour écouter l’aide, lire la liste de conférence ou désactiver eux-mêmes leur micro.

Les participants d’appels entrants (qu’ils composent le numéro ou non à partir du RTC) entendent des annonces personnelles pendant la conférence, par exemple si leur micro a ou non été désactivé, si la réunion est enregistrée ou si une personne attend dans la salle d’attente.

> [!NOTE]  
> Les participants qui se joignent à la conférence en cliquant sur un lien au lieu de composer un numéro n’entendent pas les annonces personnelles.
