---
title: Comment utiliser des écrans Microsoft Teams
ms.author: v-mdhiman
author: ManikaDhiman
manager: serdars
ms.reviewer: weizxue
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
search.appverid: MET150
localization_priority: Normal
description: Cet article fournit des instructions sur l’utilisation des panneaux Teams.
ms.openlocfilehash: eba450b42bb66dfbe202290cdd235a0d4db9e710
ms.sourcegitcommit: 6785d7f1ef5d2010ab334ec8cc46884327a53662
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/01/2021
ms.locfileid: "50395325"
---
# <a name="how-to-use-microsoft-teams-panels"></a>Utilisation des panneaux Microsoft Teams

Les panneaux Microsoft Teams sont des appareils à affichage numérique compact qui sont affichés directement en dehors de vos espaces de réunion, généralement à côté des entrées. Ces écrans tactiles sont des appareils Microsoft Teams dédiés qui offrent un aperçu rapide de votre espace de réunion et de la réunion programmée. Les indicateurs LED et Écran d’accueil aux codes de couleur dynamique vous permet de déterminer si l’espace est disponible ou réservé à distance. Vous pouvez utiliser des panneaux Teams pour réserver un espace de réunion disponible pour une réunion ad hoc, sur place.

Les écrans Teams sont préinstallés avec Microsoft Teams et affichent les détails des réunions qui sont programmés via les calendriers Outlook ou Teams.

Cet article fournit des conseils, tant aux utilisateurs finaux qu’aux administrateurs, sur l’utilisation des appareils des panneaux Teams. Il fournit également des réponses aux [questions fréquemment posées sur](#frequently-asked-questions) l’utilisation de ces appareils.

Pour une vue d’ensemble des appareils à panneaux et pour obtenir des instructions sur la façon de les planifier, de les livrer et de les gérer dans votre organisation, voir Déployer [les écrans Microsoft Teams.](teams-panels.md)

Pour un démarrage rapide, consultez les panneaux [Mise en place de Teams.](https://support.microsoft.com/office/get-started-with-teams-panels-fa5e85d1-7ff3-4f11-b0b0-277e2302c8be)

## <a name="teams-panels-end-user-experience"></a>Expérience utilisateur des panneaux Teams

Explorez [l’écran d’accueil](#explore-teams-panels-home-screen) de vos écrans Teams pour afficher l’espace de réunion et les détails de la réunion. Vous pouvez également appuyer et faire défiler le panneau de l’écran tactile pour d’autres actions.

Utilisez vos écrans Teams pour :

- [Afficher les détails et la disponibilité de l’espace de réunion, les détails des réunions, les réservations à venir](#explore-teams-panels-home-screen)
- [Réserver un espace de réunion disponible](#reserve-meeting-spaces-for-ad-hoc-meetings)
- [Signaler un problème](#report-a-problem)
- [Afficher ou mettre à jour le paramètre d’un appareil](#view-or-update-a-device-setting)

## <a name="explore-teams-panels-home-screen"></a>Écran d’accueil des panneaux Explorer Teams

L’écran d’accueil est l’interface visuelle principale de vos panneaux Teams.  

Dans l’écran d’accueil, vous pouvez afficher l’emplacement et les détails de la réunion, réserver un espace, afficher les réservations à venir et identifier l’état de disponibilité actuel.

La capture d’écran suivante montre différentes parties ou vignettes dans l’écran d’accueil des panneaux Teams :

:::image type="content" source="../media/panels-home-screen-explanation.png" alt-text="Cette capture d’écran affiche différentes zones dans l’écran d’accueil des panneaux Teams":::

Pour une description de chaque vignette, reportez-vous au tableau suivant :

Vignette | Description
:---|:---
**1-Current time, day, date, and meeting space details** | Affiche l’heure, le jour, la date et le nom de l’espace de réunion actuels. Le nom de l’espace de réunion est le nom du compte de ressource qui s’est inscrit aux panneaux.
**2-Meeting space availability and meeting details** | Indique la disponibilité de l’espace de réunion et affiche les détails de la réunion. Affichez la vignette De la disponibilité [de l’espace de réunion et des détails de la réunion.](#meeting-space-availability-and-meeting-details-tile)
**Calendrier à 3 à venir** | Affiche le calendrier de l’espace de réunion et la disponibilité pendant 24 heures à partir de l’heure actuelle. Faites défiler vers le haut ou vers le bas pour déterminer les créneaux de temps disponibles et ceux qui sont réservés.
**4-Settings** | Affiche **l’icône Paramètres.** Appuyez dessus pour signaler un problème ou mettre à jour les paramètres du périphérique disponibles.

### <a name="meeting-space-availability-and-meeting-details-tile"></a>Vignette Des informations sur la disponibilité de l’espace de réunion et les détails de la réunion

L’apparence de cette vignette et ses fonctionnalités varient en fonction de la disponibilité de l’espace de réunion et du type de réservation.

#### <a name="meeting-space-is-reserved-for-a-scheduled-meeting"></a>L’espace de réunion est réservé pour une réunion programmée

La vignette apparaît en violet pour un espace de réunion réservé à une réunion prévue (prévue via Outlook ou Teams). Il affiche le titre de la réunion dans un texte bien en évidence, les heures de début et de fin de réunion et le nom de l’organisateur de la réunion. Pour une réunion Teams, le logo Teams apparaît également. Les détails de la réunion sont bien visibles et les participants peuvent facilement vérifier qu’ils se trouver dans l’espace de réunion qui leur est accessible, au bon moment et pour la réunion qui leur est accessible.

:::image type="content" source="../media/panels-right-tile-scheduled-meeting.png" alt-text="Écran d’accueil des panneaux Teams montrant que l’espace de réunion est réservé pour une réunion programmée":::

> [!NOTE]
>
> - Après avoir planifier une réunion, la synchronisation du calendrier et son affichage sur l’écran des écrans peuvent prendre jusqu’à 90 secondes.
> - Pour une [réunion programmée marquée comme](https://support.microsoft.com/office/make-an-appointment-or-meeting-private-dc3898f0-22f5-45c6-8cc8-b4d4db84111d)privée, la réunion privée s’affiche au lieu du titre réel. 

#### <a name="meeting-space-is-reserved-for-an-ad-hoc-meeting"></a>L’espace de réunion est réservé à une réunion ad hoc

La vignette apparaît en violet pour un espace de réunion [réservé à une réunion ad hoc.](#reserve-meeting-spaces-for-ad-hoc-meetings) Il affiche le texte réservé **ainsi que** les heures de début et de fin des réunions. Lorsque vous programmez des réunions ad hoc à partir du panneau (au lieu des calendriers Outlook ou Teams), vous réservez réellement le calendrier de cet espace de réunion. Ces réunions sont automatiquement programmées en tant que réunions Teams, aussi le logo Teams s’affiche-t-il toujours à l’écran.

:::image type="content" source="../media/panels-right-tile-reserved-adhoc.png" alt-text="Écran d’accueil des panneaux Teams montrant que l’espace de réunion est réservé à une réunion ad hoc":::

#### <a name="meeting-space-is-available"></a>Un espace de réunion est disponible

La vignette apparaît en vert pour un espace de réunion disponible. Il affiche Disponible **dans un**  texte bien visible et un bouton Réserver apparaît également que vous pouvez appuyer pour réserver l’espace de réunion pour [une réunion ad hoc.](#reserve-meeting-spaces-for-ad-hoc-meetings) Vous pouvez consulter le calendrier à venir de l’espace de réunion (vignette inférieure droite) pour déterminer l’heure de fin de votre réunion ad hoc.

:::image type="content" source="../media/panels-right-tile-available-status.png" alt-text="Cette capture d’écran montre comment s’affiche l’écran d’accueil des panneaux Teams lorsque l’espace de réunion est disponible.":::

## <a name="reserve-meeting-spaces-for-ad-hoc-meetings"></a>Réserver des espaces de réunion pour les réunions ad hoc

Vous pouvez réserver un [espace de réunion](#meeting-space-is-available) disponible directement à partir de panneaux pour une réunion ad hoc. Toutes les réunions ad hoc sont automatiquement programmées en tant que réunions Teams. Toutefois, une fois réservé, vous ne pouvez pas libérer ou désserver cet espace de réunion via des panneaux. Seuls les administrateurs du compte de ressources de l’appareil peuvent annuler la réunion ad hoc (via le calendrier Outlook ou Teams) pour annuler la réservation de l’espace.

Pour les réunions ad hoc réservées directement à partir de panneaux :

- L’heure de début est toujours l’heure actuelle et, par exemple, vous ne pouvez pas la planifier pour une heure future.
- L’heure de fin peut être jusqu’à la prochaine réunion prévue ou jusqu’à 24 heures à partir de l’heure en cours, selon la date précédente. Vérifiez la **vignette Calendrier à** venir dans l’écran d’accueil pour déterminer les créneaux de temps pendant lesquels l’espace de réunion est disponible ou réservé.

Pour réserver un espace de réunion disponible pour une réunion ad hoc :

1. Dans l’écran d’accueil, appuyez sur **le bouton** Réserver.
    :::image type="content" source="../media/panels-reserve.png" alt-text="Écran d’accueil des panneaux Teams affichant le bouton Réserver":::
2. Dans **l’écran de réunion ad hoc,** examinez les options d’heure de fin disponibles. Vous pouvez utiliser les flèches droite et gauche pour parcourir les options d’heure de fin disponibles.

    :::image type="content" source="../media/panels-reserve-endtime.png" alt-text="Écran de réunion ad hoc montrant les créneaux de fin":::

    > [!Note]
    >
    > - Les options d’heure de fin sont affichées par intervalles de 15 minutes par heure.
    > - L’heure de fin est par défaut l’intervalle de 15 minutes suivant, soit au moins cinq minutes après l’heure actuelle. Par exemple, si l’heure actuelle est 13:57, l’heure de fin par défaut est de 14:15 et non de 14:00. Cela empêche les utilisateurs de réserver de l’espace pendant au moins cinq minutes. Dans la capture d’écran ci-dessus, l’heure de fin par défaut s’affiche sous la forme 14:00, soit l’intervalle de 15 minutes suivant, soit au moins cinq minutes après l’heure actuelle (13:53 PM).
    > - Une exception à la règle ci-dessus est lorsque l’heure de début de la réunion suivante est dans les cinq minutes suivant l’heure actuelle. Dans ce cas, vous pouvez réserver l’espace jusqu’à l’heure de début de la prochaine réunion. Par exemple, si l’heure actuelle est 13:57 et que l’heure de début de la prochaine réunion est 14h, alors 14h00 s’affiche comme seule option d’heure de fin et vous pouvez réserver l’espace pendant trois minutes.

3. Appuyez sur l’intervalle de temps de fin souhaité, puis appuyez sur **Réserver.**

    Une fenêtre de confirmation s’affiche avec un emoji pouce levé, l’heure de début et de fin d’une réunion et le nom de l’espace de réunion.
    :::image type="content" source="../media/panels-reserve-confirmation.png" alt-text="Message de confirmation de réunion ad hoc":::
La vignette droite de l’écran d’accueil apparaît désormais en violet et affiche le texte **réservé** et le logo Teams. Cela indique que l’espace de réunion est maintenant réservé à une réunion Teams ad hoc.
  
    :::image type="content" source="../media/panels-right-tile-reserved-adhoc.png" alt-text="Écran d’accueil montrant que l’espace de réunion est réservé à une réunion ad hoc":::

    > [!NOTE]
    > Si l’espace de réunion est  une salle Microsoft Teams, vous pouvez rejoindre cette réunion Teams avec la salle Microsoft Teams ou les appareils Surface Hub de la salle.

### <a name="report-a-problem"></a>Signaler un problème

Pour signaler un problème avec l’appareil ou l’espace de réunion, pour  demander une mise à jour des fonctionnalités ou pour fournir des commentaires, utilisez l’icône Paramètres de l’écran d’accueil.

1. Appuyez sur **l’icône d’engrenage Paramètres** dans l’écran d’accueil.

2. Appuyez sur **l’option Signaler un** problème.

    **L’écran Envoyer des** commentaires s’affiche dans un format de formulaire.
3. Dans le **type** de la demande, sélectionnez le type de demande.
4. Dans le **dossier** Problème, sélectionnez la catégorie.
5. Dans le **champ de** texte Titre, tapez le titre à l’aide du pavé numérique des panneaux.
6. Dans le champ de texte sous **Titre,** tapez des détails supplémentaires si nécessaire.

    > [!NOTE]
    > N’incluez aucune information d’identification personnelle.

7. Examinez vos entrées, puis appuyez **sur Envoyer.**

### <a name="view-or-update-a-device-setting"></a>Afficher ou mettre à jour le paramètre d’un appareil

Il existe plusieurs paramètres d’appareil, tels que l’accessibilité, le redémarrage, la politique de confidentialité, que vous pouvez afficher ou mettre à jour directement à partir de panneaux. Les paramètres d’appareil disponibles peuvent varier en fonction du fabricant d’ordinateurs (OEM) de votre appareil. Pour plus d’informations sur les paramètres spécifiques de votre appareil, consultez la documentation OEM.

Pour afficher ou mettre à jour un paramètre d’appareil :

1. Appuyez sur **l’icône Paramètres** dans l’écran d’accueil.
2. Dans **l’écran Paramètres,** appuyez **sur Paramètres de l’appareil.**
3. Dans **l’écran Paramètres de l’appareil,** appuyez sur le paramètre à afficher ou à mettre à jour.
4. Suivez l’invite à l’écran pour afficher ou mettre à jour le paramètre.

## <a name="teams-panels-admin-experience"></a>Expérience de l’administrateur des panneaux Teams

Si vous êtes l’administrateur du compte de ressources du panneau [Teams,](teams-panels.md\#resource-account-provisioning)vous êtes également l’administrateur de **l’application Panel** sur l’appareil. En tant **qu’administrateur** de l’application Panneaux, vous pouvez gérer toutes les fonctions mentionnées dans la [section](#teams-panels-end-user-experience) expérience utilisateur final, en plus de gérer les paramètres de l’application **Panneaux** sur l’appareil.

Vos périphériques de panneaux offrent deux types de paramètres d’administration. Vous devez être administrateur d’appareil pour accéder aux paramètres d’administration disponibles. Les utilisateurs finaux ne peuvent pas accéder à ces paramètres.

- Paramètres d’administration spécifiques à l’appareil, tels que l’affichage, l’heure et la date, la langue, le bluetooth, le WiFi, etc. Consultez la documentation OEM pour en savoir plus sur ces paramètres.
- Paramètres d’administration spécifiques à **l’application Panneaux** sur votre appareil, tels que le papier peint et la couleur de l’indicateur LED. Seul un administrateur de **l’application Panneaux peut** accéder à ces paramètres. Étant **donné que les** paramètres de l’application Panneaux sont disponibles dans les paramètres administrateur, vous devez avoir des informations d’identification d’administrateur pour l’appareil et l’application **Panneaux** pour accéder aux paramètres de l’application **Panneaux.**

> [!NOTE]
> Toute mise à jour des **paramètres de l’application Panneaux** effectuée via l’appareil s’applique uniquement à cet appareil spécifique. Ces mises à jour n’auront aucun impact sur les autres appareils de panneaux dans votre organisation. Par exemple, si vous modifiez l’image de papier peint de l’écran d’accueil dans les paramètres de l’application **Panneaux,** l’image de papier peint change uniquement pour cet appareil spécifique.

### <a name="access-panels-app-settings"></a>Paramètres de l’application Panneaux d’accès

Vous pouvez accéder aux **paramètres spécifiques** de l’application Panneaux à l’aide de l’option **Paramètres** de l’application Panneaux sous les paramètres d’administration. Les étapes pour accéder aux paramètres de **l’application Panneaux** peuvent différer en fonction de l’OEM de votre appareil.

Pour accéder à **l’option Paramètres de l’application Panneaux** :

1. Appuyez sur **l’icône Paramètres** dans l’écran d’accueil.
2. Dans **l’écran Paramètres,** appuyez **sur Paramètres de l’appareil.**
3. Appuyez sur **Paramètres d’administration.**

    > [!NOTE]
    > Selon le OEM de votre appareil, vous devrez peut-être entrer le mot de passe administrateur de l’appareil maintenant ou après l’étape suivante.

4. Faites défiler vers le bas pour trouver **l’option Paramètres de l’application Panneaux.** Appuyez dessus.
5. Appuyez **sur le bouton Paramètres de l’application** Panneaux sur l’écran de droite.
    L’écran avec les paramètres **de l’application Panneaux** disponibles s’affiche.

    :::image type="content" source="../media/panels-app-settings-screen.png" alt-text="Cette capture d’écran affiche l’écran avec les paramètres de l’application Panneaux disponibles":::

    Utilisez cet écran pour mettre à jour les paramètres **suivants de l’application Panneaux** pour votre appareil :

    - [Papier peint](#update-the-wallpaper)
    - [Indicateur LED](#change-the-busy-state-led-color)

#### <a name="update-the-wallpaper"></a>Mettre à jour le papier peint

Modifier l’image de papier peint de l’écran d’accueil.

1. [Paramètres **de l’application Panneaux** Access.](#access-panels-app-settings)
2. Appuyez **sur Papier peint.**
3. Dans **Choisir votre image, sélectionnez** une image à définir comme image d’arrière-plan de l’écran d’accueil. Afficher un aperçu de l’image sélectionnée sous **Arrière-plan.**
:::image type="content" source="../media/panels-wallpapers-setting.png" alt-text="Cette capture d’écran affiche l’écran des paramètres de papier peint":::
4. Revenir à l’écran d’accueil et vérifier que le papier peint est mis à jour.

#### <a name="change-the-busy-state-led-color"></a>Modifier la couleur LED de l’état occupé

Les administrateurs peuvent choisir la couleur rouge ou violette comme couleur LED pour indiquer que l’espace de réunion est occupé ou réservé. La couleur LED pour indiquer qu’un espace disponible est toujours vert et ne peut pas être modifiée.

1. [Paramètres **de l’application Panneaux** Access.](#access-panels-app-settings)
2. Appuyez **sur Paramètres LED.**
3. Dans **Choisir la couleur LED,** sélectionnez la couleur souhaitée.
:::image type="content" source="../media/panels-led-settings.png" alt-text="Cette capture d’écran présente les paramètres d’état occupé de couleur LED":::
4. Revenir à l’écran d’accueil et vérifier que la couleur LED de l’état occupé est mise à jour. Si l’espace de réunion est actuellement disponible, essayez de planifier une réunion test pour vérifier la modification de la couleur du LED pour l’état occupé.

## <a name="frequently-asked-questions"></a>Forum aux questions

Trouvez des réponses aux questions les plus fréquemment posées sur les appareils des panneaux Teams.

**À quelle distance puis-je voir les détails de la planification d’un espace de réunion ?**  
Dans  la vignette Calendrier à venir (en bas à droite) dans l’écran d’accueil, vous pouvez voir les détails de planification d’un espace de réunion pour 24 heures à partir de l’heure actuelle.

**Puis-je réserver un espace de réunion pour une durée ultérieure à partir du périphérique des panneaux Teams ?**  
Non, vous ne pouvez pas réserver d’espace de réunion pour une heure ultérieure à partir de panneaux. L’heure de début est toujours l’heure actuelle pour une réunion ad hoc prévue à partir de panneaux.

**Pendant combien de temps puis-je réserver un espace de réunion disponible pour une réunion ad hoc ?**  
Vous pouvez réserver un espace de réunion disponible à partir de l’heure actuelle jusqu’à l’heure de la prochaine réunion prévue, ou jusqu’à 24 heures à partir de l’heure actuelle (selon la date antérieure). Par exemple, si l’heure actuelle est 10 H et que l’heure de début de la prochaine réunion est de 14 h, vous pouvez réserver l’espace de réunion de 10 h à 14 h.