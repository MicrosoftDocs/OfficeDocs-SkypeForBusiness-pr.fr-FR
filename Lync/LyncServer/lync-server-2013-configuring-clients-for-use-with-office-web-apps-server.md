---
title: "Conf. des clients dans Lync Server 2013 pour l’ut. avec Office Web Apps Server"
TOCTitle: Configuration des clients pour l’utilisation avec Office Web Apps Server
ms:assetid: e5eaead7-0b32-42fb-97eb-ca203af59a9d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ205339(v=OCS.15)
ms:contentKeyID: 49299170
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration des clients dans Lync Server 2013 pour l’utilisation avec Office Web Apps Server

 

_**Dernière rubrique modifiée :** 2013-02-25_

Afin que les utilisateurs bénéficient de toutes les fonctionnalités d’Office Web App Server, mettez-les à niveau vers Microsoft Lync 2013 ; seuls les utilisateurs de Lync 2013 peuvent, entre autres, explorer des diapositives PowerPoint indépendamment de la présentation PowerPoint en elle-même. (Autrement dit, ils peuvent regarder n’importe quelle diapositive de la présentation à tout moment, sans interférer de quelque manière que ce soit avec la présentation réelle.) Les utilisateurs qui n’utilisent pas Lync 2013 pourront toujours participer à des conférences en ligne et voir la présentation PowerPoint ; cependant, ils ne pourront pas explorer les diapositives indépendamment, ni voir les transitions entre diapositives ou les vidéos incorporées.

Notez que ces fonctionnalités seront toujours disponibles pour les utilisateurs de Lync 2013, et ce même si le présentateur PowerPoint exécute Microsoft Lync 2010. Si une présentation PowerPoint est hébergée par un utilisateur exécutant Lync 2010, Lync Server 2013 se coordonne avec Office Web Apps Server pour faire en sorte que les utilisateurs Lync 2013 voient la version d’Office Web Apps Server de cette présentation. Office Web Apps Server ne fournit pas de services PowerPoint pour les utilisateurs exécutant des clients différents de Lync 2013. Ces utilisateurs se connectent au service du serveur de conférence à la place, et voient les présentations PowerPoint de la même façon que dans Microsoft Lync Server 2010. Cela signifie également que ces utilisateurs auront accès uniquement à des fonctionnalités offertes par Lync Server 2010 plus limitées.

Bien qu’aucune configuration cliente ne soit requise pour Office Web Apps Server (autre que la mise à niveau vers Lync 2013), il est recommandé que les participants à la conférence mettent à niveau vers Internet Explorer 9. Les conférences peuvent être accédées via Internet Explorer 8, mais cela comporte certaines limites. Par exemple, les utilisateurs de ce navigateur ne peuvent pas redimensionner la fenêtre PowerPoint de manière personnalisée ; ils sont limités à l؊’utilisation de l’une des trois tailles de fenêtre prédéfinies. Ils ne peuvent pas non plus lire des fichiers multimédia.

