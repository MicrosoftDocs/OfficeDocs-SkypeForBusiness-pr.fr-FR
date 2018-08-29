---
title: Création de la conception de topologie initiale pour Skype Entreprise Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 4/5/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f3131153-de14-41be-b1e6-7d4bb0191af1
description: Une fois que vous avez terminé l’installation le Skype pour l’outil de planification de Business Server, vous êtes prêt à démarrer l’outil de planification et de commencer à concevoir la proposé Skype pour infrastructure Business Server 2015.
ms.openlocfilehash: 73fd6f4a83ec5aec6808124728c1c73419bcdd28
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23246665"
---
# <a name="create-the-initial-topology-design-for-skype-for-business-server-2015"></a>Création de la conception de topologie initiale pour Skype Entreprise Server 2015

Une fois que vous avez terminé l’installation le Skype pour l’outil de planification de Business Server, vous êtes prêt à démarrer l’outil de planification et de commencer à concevoir la proposé Skype pour infrastructure Business Server 2015.

> [!NOTE]
>  L’outil de planification est un outil Assistants avec guides détaillés pour informer votre processus de décision dans la conception de vos sites et la topologie. Cette rubrique est destinée pas comme un guide exhaustif, mais simplement pour vous aider à commencer à utiliser l’outil de planification de vos sessions de conception.

### <a name="to-get-started-using-the-planning-tool-and-create-the-initial-design"></a>Pour commencer à utiliser l’outil de planification et de créer la conception initiale

1. Démarrer le Skype pour l’outil de planification de Business Server 2015 : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business Server 2015**, puis cliquez sur **Outil de planification**.

2. Après le démarrage de l’outil de planification, la page **Bienvenue dans l’outil de planification pour Skype pour Business Server 2015** apparaît. Choisissez l’une des options suivantes pour commencer votre conception :

   - **Option 1 : mise en route** En cliquant sur la **Mise en route** fournit une série de questions avec les sélections appropriées pour définir les critères spécifique. Lorsque vous en avez terminé avec la section **Mise en route** initiale, poursuivez avec **Concevoir des sites** pour définir l’architecture de votre site. Pour achever cette option, passez à l’étape 3.

   - **Option 2 : concevoir des Sites** En cliquant sur la **Conception de Sites** au niveau de la page d’accueil ignore aux questions présentées dans la section **Mise en route** . Les informations collectées par les réponses fournies aux questions d’entretien dans la rubrique **Mise en route** sont définies comme valeurs par défaut avec cette option. En cliquant sur **Concevoir des sites**, le concepteur expérimenté peut contourner l’entretien initial et modifier les valeurs par défaut selon ses besoins sur la page de démarrage **Sites centraux**. Pour achever cette option, ignorez les étapes 3 à 5 et passez directement à l’étape 6.

   - **Option 3 : afficher votre topologie enregistrée** Si vous avez déjà effectué et enregistré une topologie à l’aide précédente de l’outil de planification, vous pouvez ignorer la plupart de ces étapes et démarrer à l’ouverture et l’affichage de la topologie. Vous pouvez également apporter des modifications et des mises à jour à la topologie, la ré-enregistrer, puis l’exporter dans Microsoft Excel ou Microsoft Visio. Pour achever cette option, ignorez les étapes 3 à 12 et passez directement à l’étape 13.

3. Cliquez sur **Démarrer** pour commencer à concevoir votre Skype pour topologie Business Server 2015.

4. Répondez à chaque rubrique en sélectionnant les critères appropriés pour votre conception, puis cliquez sur **Suivant** pour passer à la page suivante de l’Assistant. Cliquez sur **Précédent** pour modifier les pages précédentes.

    > [!TIP]
    > Chaque page contient une description des critères de sélection et des recommandations basées sur les pratiques préférées et la planification de la capacité. Si vous avez besoin de plus de détails, cliquez sur **en savoir plus** pour lire des informations détaillées de la Skype pour la documentation de planification de Business Server 2015 sur le site Web Microsoft. Vous devez disposer de la connectivité Internet pour accéder au site Web de Microsoft.

5. Sélectionnez les options appropriées pour votre conception. Une fois les critères initiaux définis, une page viendra confirmer que votre vue d’ensemble des fonctionnalités est complète.

6. Cliquez sur **Sites de création** pour définir votre site central.

    > [!NOTE]
    > Chaque Skype pour topologie Business Server 2015 ont au moins un site central. Votre conception peut avoir un seul site central, un site central avec un nombre de sites de succursale, un nombre de sites centraux ou un nombre de sites centraux avec les sites de succursale associés à chaque site central.

7. Dans **Nom du Site**, tapez le nom qui identifiera ce site central.

8. Dans la zone **Utilisateurs hébergés du Site**, tapez le nombre prévu d’utilisateurs simultanés sur site hébergés dans ce site central.

9. **Les utilisateurs hébergés sur le nuage**, tapez le nombre prévu d’utilisateurs simultanés en ligne hébergés dans ce site central.

10. Modifiez les sélections pour Collaboration en ligne, Utilisateurs, Voix, Options de déploiement supplémentaires ou Applications serveur, selon les besoins.

    > [!IMPORTANT]
    > Ce n’est qu’à ce moment de la conception que vous pouvez activer ou désactiver les options de votre déploiement. Toutefois, vous pouvez configurer plusieurs options dans une phase ultérieure de l’outil de planification. Certaines options sont également indisponibles et ne peuvent pas être désactivées. En outre, vous pouvez être amené à désactiver une option pour en désactiver une autre. Par exemple, si vous désactivez l’option **Voix Entreprise** sous Voix, les options **Response Group**, **Annonce** et **Parcage d’appel** sous Applications serveur (toutes étant des fonctionnalités de Voix Entreprise) sont également désactivées.

11. Après avoir défini le nom du site et le nombre d’utilisateurs, cliquez sur **Suivant**.

12. Les pages suivantes de demanderont des informations sur SIP domaines, paramètres de conférence, paramètres de la voix et l’infrastructure, la messagerie unifiée Exchange, l’accès des utilisateurs externes, conversation permanente paramètres, paramètres du client, possibilités de colocalisation et les sites de succursale. Répondez à toutes ces questions selon le cas.

13. La question finale vous demande si vous souhaitez créer un autre site central. Si vous sélectionnez **Oui**, l’outil de planification renvoie à la page Sites centraux. Si vous sélectionnez **Non**, cliquez sur **Suivant**, puis sur **Dessiner** pour afficher la vue Topologie globale de niveau supérieur.

14. Pour afficher la topologie existante, cliquez sur **Afficher**.

15. Cliquez sur le fichier .xml qui représente la topologie précédemment enregistrée, puis cliquez sur **Ouvrir**.

16. L’outil de planification affiche la page topologie globale. Vous pouvez commencer la modification, la mise à jour ou modification de la topologie en utilisant les outils disponibles dans l’outil de planification.

## <a name="see-also"></a>Voir aussi

[Modification de la conception](https://technet.microsoft.com/library/08f639ba-0e5f-4ae7-9191-c3d96c25b169.aspx)