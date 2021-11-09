---
title: Créer la conception de topologie initiale pour Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: f3131153-de14-41be-b1e6-7d4bb0191af1
description: Une fois que vous avez terminé l’installation de l’outil de planification Skype Entreprise Server, vous êtes prêt à démarrer l’outil de planification et à commencer à concevoir l’infrastructure Skype Entreprise Server 2015 proposée.
ms.openlocfilehash: 85bbab87696f01e00ccbd9b5e413329a52a7cd22
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60863481"
---
# <a name="create-the-initial-topology-design-for-skype-for-business-server-2015"></a>Créer la conception de topologie initiale pour Skype Entreprise Server 2015

Une fois que vous avez terminé l’installation de l’outil de planification Skype Entreprise Server, vous êtes prêt à démarrer l’outil de planification et à commencer à concevoir l’infrastructure Skype Entreprise Server 2015 proposée.

> [!NOTE]
>  L’outil de planification est un outil piloté par un Assistant avec des guides détaillés pour vous aider à prendre des décisions lors de la conception de vos sites et de votre topologie. Cette rubrique n’est pas destinée à être un guide exhaustif, mais simplement à vous aider à commencer à utiliser l’outil de planification dans vos sessions de conception.

### <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a>Pour commencer à utiliser l’Outil de planification et à créer la conception initiale

1. Démarrez l Skype Entreprise Server de planification 2015 : cliquez sur **Démarrer,** sur Tous les **programmes,** sur **Skype Entreprise Server 2015,** puis sur Outil de **planification.**

2. Une fois l’outil de planification démarré, la page Bienvenue dans l’outil de planification **Skype Entreprise Server 2015** s’affiche. Choisissez l’une des options suivantes pour commencer votre conception :

   - **Option 1 : Prise en main** Cliquer sur **Prise en main** fournit une série spécifique de questions d’entretien avec des sélections pertinentes pour définir les critères. Lorsque vous en avez terminé avec la section **Démarrage** initiale, poursuivez avec **Concevoir des sites** pour définir l’architecture de votre site. Pour achever cette option, passez à l’étape 3.

   - **Option 2 : Concevoir des sites** Cliquer sur **Concevoir des sites** sur la page d’accueil contourne les questions d’entretien présentées dans **Prise en main** section. Les informations qui auraient été rassemblées en répondant aux questions de l’entretien dans Prise en main **section** sont définies sur les valeurs par défaut avec cette option. En cliquant **sur Sites** de conception, le concepteur expérimenté peut ignorer l’entretien initial et modifier les valeurs par défaut, selon les besoins, sur la page d’accueil **des Sites** centraux. Pour achever cette option, ignorez les étapes 3 à 5 et passez directement à l’étape 6.

   - **Option 3 : Afficher votre topologie enregistrée** Si vous avez déjà terminé et enregistré une topologie par le biais d’une utilisation précédente de l’outil de planification, vous pouvez ignorer la plupart de ces étapes et commencer par ouvrir et afficher la topologie. Vous pouvez également apporter des modifications et des mises à jour à la topologie, la réasserrez, puis l’exporter vers Microsoft Excel ou Microsoft Visio. Pour achever cette option, ignorez les étapes 3 à 12 et passez directement à l’étape 13.

3. Cliquez **Prise en main** pour commencer à concevoir votre topologie Skype Entreprise Server 2015.

4. Répondez à chaque rubrique en sélectionnant les critères appropriés pour votre conception, puis cliquez sur **Suivant** pour passer à la page suivante de l’Assistant. Cliquez **sur Précédent** pour apporter des modifications sur les pages précédentes.

    > [!TIP]
    > Chaque page contient une description des critères de sélection et des recommandations basées sur les pratiques préférées et la planification de la capacité. Si vous avez besoin  de détails supplémentaires, cliquez sur En savoir plus pour lire des informations détaillées dans la documentation de planification Skype Entreprise Server 2015 sur le site web Microsoft. Vous devez avoir une connectivité Internet pour accéder au site web de Microsoft.

5. Sélectionnez les options appropriées pour votre conception. Une fois les critères initiaux définis, une page viendra confirmer que votre vue d’ensemble des fonctionnalités est complète.

6. Cliquez **sur Concevoir des sites** pour définir votre site central.

    > [!NOTE]
    > Chaque Skype Entreprise Server topologie 2015 aura au moins un site central. Votre conception peut avoir un site central unique, un site central avec un certain nombre de sites de succursale, un certain nombre de sites centraux ou un certain nombre de sites centraux avec des sites de succursale associés à chaque site central.

7. Dans **Nom du** site, tapez le nom qui identifiera ce site central.

8. Dans **Utilisateurs du site d’accueil,** tapez le nombre attendu d’utilisateurs simultanés locaux qui seront homed dans ce site central.

9. Dans **Utilisateurs d’accueil** cloud, tapez le nombre attendu d’utilisateurs simultanés en ligne qui seront homed dans ce site central.

10. Modifiez les sélections pour la collaboration en ligne, les utilisateurs, la voix, les options de déploiement supplémentaires ou les applications serveur, selon vos besoins.

    > [!IMPORTANT]
    > À ce stade de la conception, vous pouvez uniquement sélectionner ou effacer des options pour votre déploiement. Toutefois, vous pouvez configurer d’autres options dans une phase ultérieure de l’outil de planification. Certaines options sont également indisponibles et ne peuvent pas être désactivées. En outre, vous pouvez être amené à désactiver une option pour en désactiver une autre. Par exemple, si vous clear the **Voix Entreprise** option under Voice, then the **Response Group**, **Announcement**, and **Call Park** options under Server Applications (all of which are features of Voix Entreprise) are also cleared.

11. Après avoir défini le nom du site et le nombre d’utilisateurs, cliquez sur **Suivant**.

12. Les pages suivantes vous demandent des informations sur les domaines SIP, les paramètres de conférence, les paramètres de voix et l’infrastructure, la messagerie un Exchange, l’accès des utilisateurs externes, les paramètres de conversation permanente, les paramètres clients, les options de césure et les sites de succursale. Répondez à toutes ces questions selon le cas.

13. La dernière question vous demande si vous souhaitez créer un autre site central. Si vous sélectionnez **Oui,** l’outil de planification revient à la page Sites centraux. Si vous **sélectionnez Non,** cliquez  **sur Suivant,** puis cliquez sur Dessiner pour afficher la vue topologie globale de haut niveau.

14. Pour afficher une topologie existante, cliquez sur **Afficher.**

15. Cliquez sur le fichier .xml qui représente la topologie précédemment enregistrée, puis cliquez sur **Ouvrir**.

16. L’outil de planification affiche la page Topologie globale. Vous pouvez maintenant commencer à modifier, mettre à jour ou modifier la topologie à l’aide des outils disponibles dans l’outil de planification.

## <a name="see-also"></a>Voir aussi

[Modification de la conception](/previous-versions/office/lync-server-2013/lync-server-2013-editing-the-design)