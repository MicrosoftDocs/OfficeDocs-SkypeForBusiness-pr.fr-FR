---
title: Comment utiliser des panneaux Microsoft Teams panneaux
ms.author: czawideh
author: cazawideh
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
ms.localizationpriority: medium
description: Cet article fournit des conseils sur l’utilisation des panneaux Teams panneaux.
ms.openlocfilehash: 2928bb64881cad5fb5c6615d26767e963f725dcd
ms.sourcegitcommit: 2ce3e95401ac06c0370a54862372a94ec6291d01
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/05/2022
ms.locfileid: "64643038"
---
# <a name="how-to-use-microsoft-teams-panels"></a>Utilisation de panneaux Microsoft Teams panneaux

Microsoft Teams panneaux sont des écrans numériques compacts, installés directement en dehors de vos espaces de réunion, en général à côté des entrées. Ces écrans à écran tactile sont dédiés Microsoft Teams’appareils qui offrent un aperçu rapide de votre espace de réunion et de la réunion programmée. Les indicateurs LED et Écran d’accueil aux codes de couleur dynamique vous permet de déterminer si l’espace est disponible ou réservé à distance. Vous pouvez utiliser Teams panneaux pour réserver un espace de réunion disponible pour une réunion ad hoc, sur place.

Teams panneaux sont préinstallés avec des Microsoft Teams et affichent les détails des réunions qui sont programmés via Outlook calendriers Teams calendriers.

Cet article fournit des conseils, tant aux utilisateurs finaux qu’aux administrateurs, sur l’utilisation des panneaux Teams panneaux. Il fournit également des réponses aux [questions fréquemment posées](#frequently-asked-questions) sur l’utilisation de ces appareils.

Pour une vue d’ensemble des périphériques en panneaux et pour obtenir des instructions sur la façon de les planifier, de les livrer et de les gérer dans votre organisation, voir Déployer [Microsoft Teams panneaux](teams-panels.md).

Pour un démarrage rapide, découvrez les [Démarrage’Teams panneaux](https://support.microsoft.com/office/get-started-with-teams-panels-fa5e85d1-7ff3-4f11-b0b0-277e2302c8be).

## <a name="teams-panels-end-user-experience"></a>Teams panneaux expérience utilisateur final

Explorez [l’écran d’accueil](#explore-teams-panels-home-screen) de Teams panneaux pour afficher l’espace de réunion et les détails de la réunion. Vous pouvez également appuyer et faire défiler le panneau de l’écran tactile pour d’autres actions.

Utilisez vos panneaux Teams panneaux pour :

- [Afficher les détails et la disponibilité de l’espace de réunion, les détails des réunions, les réservations à venir](#explore-teams-panels-home-screen)
- [Réserver un espace de réunion disponible](#reserve-meeting-spaces-for-ad-hoc-meetings)
- [Signaler un problème](#report-a-problem)
- [Afficher ou mettre à jour un paramètre d’appareil](#view-or-update-a-device-setting)

## <a name="explore-teams-panels-home-screen"></a>Explorer Teams écran d’accueil des panneaux

L’écran d’accueil est l’interface visuelle principale de Teams panneaux.  

Dans l’écran d’accueil, vous pouvez afficher l’emplacement et les détails de la réunion, réserver un espace, afficher les réservations à venir et identifier l’état de disponibilité actuel.

La capture d’écran suivante montre différentes parties ou vignettes dans l’écran d Teams’accueil des panneaux :

:::image type="content" source="../media/panels-home-screen-explanation.png" alt-text="Cette capture d’écran affiche différentes zones sur les différents écrans Teams’accueil.":::

Pour une description de chaque vignette, reportez-vous au tableau suivant :

Vignette | Description
:---|:---
**1-Current time, day, date, and meeting space details** | Affiche l’heure, le jour, la date et le nom de l’espace de réunion actuels. Le nom de l’espace de réunion est le nom du compte de ressource qui s’est inscrit aux panneaux.
**2-Meeting space availability and meeting details** | Indique la disponibilité de l’espace de réunion et affiche les détails de la réunion. Affichez [la vignette De la disponibilité de l’espace de réunion et des détails de la réunion](#meeting-space-availability-and-meeting-details-tile).
**Calendrier à 3 à venir** | Affiche le calendrier de l’espace de réunion et la disponibilité pendant 24 heures à partir de l’heure actuelle. Faites défiler vers le haut ou vers le bas pour déterminer les créneaux de temps disponibles et ceux qui sont réservés.
**4-Paramètres** | Affiche **l’icône Paramètres’affichage**. Appuyez dessus pour signaler un problème ou mettre à jour les paramètres du périphérique disponibles.

### <a name="meeting-space-availability-and-meeting-details-tile"></a>Vignette Disponibilité de l’espace de réunion et détails de la réunion

L’apparence de cette vignette et ses fonctionnalités varient en fonction de la disponibilité de l’espace de réunion et du type de réservation.

#### <a name="meeting-space-is-reserved-for-a-scheduled-meeting"></a>L’espace de réunion est réservé pour une réunion programmée

La vignette apparaît en violet pour un espace de réunion réservé à une réunion prévue (Outlook ou Teams). Il affiche le titre de la réunion dans un texte bien en évidence, les heures de début et de fin de réunion et le nom de l’organisateur de la réunion. Pour une Teams, le logo Teams’affiche également. Les détails de la réunion sont bien visibles et les participants peuvent facilement vérifier qu’ils se trouver dans l’espace de réunion qui leur est accessible, au bon moment et pour la réunion qui leur est accessible.

:::image type="content" source="../media/panels-right-tile-scheduled-meeting.png" alt-text="Teams écran d’accueil montrant que l’espace de réunion est réservé pour une réunion programmée.":::

> [!NOTE]
>
> - Après avoir programmé une réunion, la synchronisation du calendrier et son affichage sur l’écran des écrans peuvent prendre jusqu’à 90 secondes.
> - Pour une [réunion programmée marquée comme](https://support.microsoft.com/office/make-an-appointment-or-meeting-private-dc3898f0-22f5-45c6-8cc8-b4d4db84111d) **privée, la** réunion privée s’affiche au lieu du titre réel.

#### <a name="meeting-space-is-reserved-for-an-ad-hoc-meeting"></a>L’espace de réunion est réservé à une réunion ad hoc

La vignette apparaît en violet pour un espace de réunion [réservé à une réunion ad hoc](#reserve-meeting-spaces-for-ad-hoc-meetings). Il affiche le texte réservé **ainsi** que les heures de début et de fin de la réunion. Les réunions ad hoc sont automatiquement programmées au cours Teams réunions. Par conséquent, le logo Teams s’affiche toujours à l’écran.

:::image type="content" source="../media/panels-right-tile-reserved-adhoc.png" alt-text="Teams écran d’accueil montrant que l’espace de réunion est réservé à une réunion ad hoc.":::

#### <a name="meeting-space-is-available"></a>Un espace de réunion est disponible

La vignette apparaît en vert pour un espace de réunion disponible. Il affiche Le **texte mis en** évidence et un bouton  Réserver apparaît également, que vous pouvez appuyer pour réserver l’espace de réunion pour [une réunion ad hoc](#reserve-meeting-spaces-for-ad-hoc-meetings). Vous pouvez consulter le calendrier à venir de l’espace de réunion (vignette inférieure droite) pour déterminer l’heure de fin de votre réunion ad hoc.

:::image type="content" source="../media/panels-right-tile-available-status.png" alt-text="Cette capture d’écran montre l’Teams’écran d’accueil des panneaux lorsque l’espace de réunion est disponible.":::

## <a name="reserve-meeting-spaces-for-ad-hoc-meetings"></a>Réserver des espaces de réunion pour les réunions ad hoc

Vous pouvez réserver un [espace de réunion](#meeting-space-is-available) disponible directement à partir de panneaux pour une réunion ad hoc. Toutes les réunions ad hoc sont automatiquement Teams réunions. Toutefois, une fois réservé, vous ne pouvez pas libérer ou désserver cet espace de réunion via des panneaux. Seuls les administrateurs du compte de ressources de l’appareil peuvent annuler la réunion ad hoc (via Outlook ou Teams calendrier) pour annuler la réservation de l’espace.

Pour les réunions ad hoc réservées directement à partir de panneaux :

- L’heure de début est toujours l’heure actuelle et, par exemple, vous ne pouvez pas la planifier pour une heure future.
- L’heure de fin peut être jusqu’à la prochaine réunion prévue ou jusqu’à 24 heures à partir de l’heure en cours, selon la date précédente. Vérifiez la **vignette Calendrier à** venir sur l’écran d’accueil pour déterminer les créneaux de temps pendant lesquels l’espace de réunion est disponible ou réservé.

Pour réserver un espace de réunion disponible pour une réunion ad hoc :

1. Dans l’écran d’accueil, appuyez sur **le bouton** Réserver.
    :::image type="content" source="../media/panels-reserve.png" alt-text="Teams écran d’accueil des panneaux montrant le bouton Réserver.":::
2. Dans **l’écran de réunion ad hoc** , examinez les options d’heure de fin disponibles. Vous pouvez utiliser les flèches droite et gauche pour parcourir les options d’heure de fin disponibles.

    :::image type="content" source="../media/panels-reserve-endtime.png" alt-text="Écran de réunion ad hoc montrant les créneaux de fin.":::

    > [!Note]
    >
    > - Les options d’heure de fin sont affichées par intervalles de 15 minutes par heure.
    > - L’heure de fin est par défaut l’intervalle de 15 minutes suivant, soit au moins cinq minutes après l’heure actuelle. Par exemple, si l’heure actuelle est 13:57, l’heure de fin par défaut est 14:15 et non 14:00. Cela empêche les utilisateurs de réserver de l’espace pendant au moins cinq minutes. Dans la capture d’écran ci-dessus, l’heure de fin par défaut s’affiche sous la forme 14:00, soit l’intervalle de 15 minutes suivant, soit au moins cinq minutes après l’heure actuelle (13:53 PM).
    > - Une exception à la règle ci-dessus est lorsque l’heure de début de la réunion suivante est dans les cinq minutes suivant l’heure actuelle. Dans ce cas, vous pouvez réserver de l’espace jusqu’à l’heure de début de la prochaine réunion. Par exemple, si l’heure actuelle est 13:57 et que l’heure de début de la prochaine réunion est 14h, alors 14h00 s’affiche comme seule option d’heure de fin et vous pouvez réserver l’espace pendant trois minutes.

3. Appuyez sur l’intervalle de temps de fin souhaité, puis appuyez sur **Réserver**.

    Une fenêtre de confirmation s’affiche avec un emoji pouce levé, l’heure de début et de fin d’une réunion et le nom de l’espace de réunion.
    :::image type="content" source="../media/panels-reserve-confirmation.png" alt-text="Message de confirmation de réunion ad hoc.":::
La vignette droite de l’écran d’accueil apparaît désormais en violet et  affiche le texte réservé et Teams logo. Cela indique que l’espace de réunion est maintenant réservé à une Teams réunion.
  
    :::image type="content" source="../media/panels-right-tile-reserved-adhoc.png" alt-text="Écran d’accueil montrant que l’espace de réunion est réservé à une réunion ad hoc.":::

    > [!NOTE]
    > Si l’espace de réunion est une salle de réunion Microsoft Teams,  vous pouvez rejoindre cette Teams réunion avec la salle de réunion Microsoft Teams salle ou Surface Hub périphériques.

### <a name="report-a-problem"></a>Signaler un problème

Pour signaler un problème avec l’appareil ou l’espace de réunion, demander une mise à jour des fonctionnalités ou fournir des  commentaires, utilisez l’icône Paramètres de l’écran d’accueil.

1. Appuyez sur **l Paramètres** de l’icône d’engrenage dans l’écran d’accueil.

2. Appuyez sur **l’option Signaler un** problème.

    **L’écran Envoyer des** commentaires s’affiche dans un format de formulaire.
3. Dans le **type** de la demande, sélectionnez le type de demande.
4. Dans **le dossier** Problème, sélectionnez la catégorie.
5. Dans le **champ de** texte Titre, tapez le titre à l’aide du pavé numérique des panneaux.
6. Dans le champ de texte sous **Titre**, tapez des détails supplémentaires si nécessaire.

    > [!NOTE]
    > N’incluez aucune information d’identification personnelle.

7. Examinez vos entrées, puis appuyez **sur Envoyer**.

### <a name="view-or-update-a-device-setting"></a>Afficher ou mettre à jour un paramètre d’appareil

Vous pouvez afficher ou mettre à jour directement à partir de panneaux plusieurs paramètres d’appareil, tels que l’accessibilité, le redémarrage et la politique de confidentialité. Les paramètres d’appareil disponibles peuvent varier en fonction du fabricant d’ordinateurs (OEM) de votre appareil. Pour plus d’informations sur les paramètres spécifiques de votre appareil, consultez la documentation OEM.

Pour afficher ou mettre à jour un paramètre d’appareil :

1. Appuyez sur **l Paramètres** de l’écran d’accueil.
2. Dans **l’Paramètres**' écran, appuyez sur **Paramètres de l’appareil**.
3. Dans **l’écran Paramètres’appareil**, appuyez sur le paramètre à afficher ou à mettre à jour.
4. Suivez l’invite à l’écran pour afficher ou mettre à jour le paramètre.

## <a name="teams-panels-admin-experience"></a>Teams’administration des panneaux

Si vous êtes l’administrateur du écran Teams des ressources, vous êtes également [l’administrateur](teams-panels.md\#resource-account-provisioning) de **l’application Panneaux** sur l’appareil. En tant **qu’administrateur** de l’application Panneaux, vous pouvez gérer toutes les fonctions mentionnées dans [la section expérience](#teams-panels-end-user-experience) utilisateur final, en plus  de gérer les paramètres de l’application Panneaux sur l’appareil.

Les appareils de vos panneaux offrent deux types de paramètres d’administration. Vous devez être administrateur d’appareil pour accéder aux paramètres d’administration disponibles. Les utilisateurs finaux ne peuvent pas accéder à ces paramètres.

- Paramètres d’administration spécifiques à l’appareil, tels que l’affichage, l’heure et la date, la langue, bluetooth, WiFi, etc. Consultez la documentation OEM pour en savoir plus sur ces paramètres.
- Paramètres d’administration spécifiques à **l’application Panneaux** sur votre appareil, tels que le papier peint et la couleur de l’indicateur LED. Seul un administrateur de **l’application Panneaux peut** accéder à ces paramètres. Étant **donné que les** paramètres de l’application Panneaux sont disponibles dans les paramètres administrateur, vous devez avoir des informations d’identification d’administrateur pour l’appareil et l’application **Panneaux** pour accéder aux paramètres de l’application **Panneaux** .

> [!NOTE]
> Toute mise à jour des **paramètres de l’application Panneaux** effectuée via l’appareil s’applique uniquement à cet appareil spécifique. Ces mises à jour n’auront aucun impact sur les autres appareils de panneaux dans votre organisation. Par exemple, si vous modifiez l’image de papier peint de l’écran d’accueil dans les paramètres de l’application **Panneaux** , l’image de papier peint change uniquement pour cet appareil spécifique.

### <a name="access-panels-app-settings"></a>Paramètres de l’application Panneaux Access

Vous pouvez accéder aux **paramètres spécifiques** de l’application Panneaux à l’aide de **l’option Paramètres** panneaux sous les paramètres d’administration. Les étapes pour accéder **aux panneaux d Paramètres** varient en fonction de l’OEM de votre appareil.

Pour accéder à **l’option d** Paramètres de l’application Panneaux :

1. Appuyez sur **l Paramètres** de l’écran d’accueil.
2. Sur **l’Paramètres**' écran, appuyez sur **Paramètres de l’appareil**.
3. Appuyez sur **le panneau Paramètres**.

    > [!NOTE]
    > Selon le OEM de votre appareil, vous devrez peut-être entrer le mot de passe administrateur de l’appareil maintenant ou après l’étape suivante.

4. Faites défiler vers le bas **jusqu’à trouver l’option Paramètres** panneaux. Appuyez dessus.
5. Appuyez **sur le bouton droit Paramètres’application** Panneaux sur l’écran droit.
    L’écran avec les paramètres **de l’application Panneaux** disponibles s’affiche.

    :::image type="content" source="../media/panels-app-settings-screen.png" alt-text="Cette capture d’écran affiche l’écran avec les paramètres de l’application Panneaux disponibles.":::

    Utilisez cet écran pour mettre à jour les paramètres **suivants de l’application Panneaux** pour votre appareil :

    - [Papier peint](#update-the-wallpaper)
    - [Indicateur LED](#change-the-busy-state-led-color)

#### <a name="pair-a-teams-panel-with-a-microsoft-teams-room-on-android"></a>Coupler un écran Teams avec une salle Microsoft Teams sur Android

Pour coupler un écran Teams et Teams Salle sur Android, les deux appareils doivent être connectés au même compte de ressource.

Sur le écran Teams, connectez-vous à l’aide de vos informations d’identification d’administrateur.

1. Go to **Paramètres > Device Paramètres > Admin Paramètres > Panels App Paramètres > Meetings > Device Pairing.**

2. Un code à six chiffres s’affiche sur la salles Teams avant de la salle avec Android. Entrez le code dans le Teams panneau.  

#### <a name="meeting-check-in-and-room-release"></a>Enregistrement de réunion et publication de salle

Les paramètres d’enregistrement et de publication de salles peuvent aider les utilisateurs à se rendre à une réunion sur des Teams de la salle qu’ils ont réservée au début de la réunion. Si un utilisateur ne vérifie pas dans un délai donné après l’heure de début de la réunion, la salle est libéré et mise à la disposition d’autres personnes.

Lorsque Teams panneaux est couplé avec une salle Microsoft Teams sur Android, les notifications d’enregistrement peuvent être activées pour s’afficher sur l’écran avant de la salle lorsque les réunions sont en retard.

Pour activer l’enregistrement et la publication de salles, consultez l’enregistrement et la publication des salles [sur Microsoft Teams panneaux](check-in-and-room-release.md).

#### <a name="room-capacity-warning"></a>Avertissement sur la capacité des salles

Teams panneaux couplés à une salle Teams sur Android peuvent afficher un message d’avertissement lorsqu’une salle de réunion a la capacité maximale ou maximale. Pour utiliser cette fonctionnalité, la salle Teams doit être dispose d’une caméra qui prend en charge le comptage de personnes. salles Teams sur Android prendre en charge les avertissements de capacité des salles sans écran Teams.

Les avertissements de capacité des salles sont désactivés par défaut. Pour activer le paramètre à partir de la écran Teams, couplez d’abord une écran Teams [à une salle Microsoft Teams sur Android](#pair-a-teams-panel-with-a-microsoft-teams-room-on-android). Le panneau et Teams de réunion doivent être signés dans le même compte de ressource.

 Ensuite, allez à la **Paramètres > paramètres de l’appareil > d’administration et > d’application du Panneau d’administration**. Ensuite, sous **Réunions**, activer la notification de occupation de salle **maximale**.

#### <a name="view-room-equipment"></a>Afficher l’équipement des salles

Lorsque cette fonctionnalité est désactivée, les utilisateurs finaux peuvent voir l’équipement disponible dans un espace sur une écran Teams.

Cette fonctionnalité est off par défaut et peut être activée par appareil. Pour l’activer, utilisez [Set-Place](/powershell/module/exchange/set-place?view=exchange-ps) dans PowerShell pour `AudioDeviceName``DisplayDeviceName`configurer les noms d’affichage pour , `VideoDeviceName`, et `Tags``IsWheelChairAccessible`.

Vous pouvez également activer cette fonctionnalité dans le Exchange d’administration. Pour [plus d’informations, voir](/exchange/recipients-in-exchange-online/manage-resource-mailboxes#edit-a-resource) Modifier une ressource.



#### <a name="update-the-wallpaper"></a>Mettre à jour le papier peint

Modifier l’image de papier peint de l’écran d’accueil.

1. [**Panneaux d’accès Paramètres**](#access-panels-app-settings).
2. Appuyez **sur Papier peint**.
3. Dans **Choisir votre image, sélectionnez** une image à définir comme image d’arrière-plan de l’écran d’accueil. Afficher un aperçu de l’image sélectionnée sous **Arrière-plan**.
:::image type="content" source="../media/panels-wallpapers-setting.png" alt-text="Cette capture d’écran affiche l’écran des paramètres de papier peint.":::
4. Retour’écran d’accueil et vérifiez que le papier peint est mis à jour.

#### <a name="change-the-busy-state-led-color"></a>Modifier la couleur LED de l’état occupé

Les administrateurs peuvent choisir la couleur rouge ou violette comme couleur LED pour indiquer que l’espace de réunion est occupé ou réservé. La couleur LED pour indiquer qu’un espace disponible est toujours vert et ne peut pas être modifiée.

1. [**Panneaux d’accès Paramètres**](#access-panels-app-settings).
2. **Appuyez sur LED Paramètres**.
3. **Sélectionnez la couleur souhaitée dans** Choisir la couleur LED.
:::image type="content" source="../media/panels-led-settings.png" alt-text="Cette capture d’écran affiche les paramètres d’état Occupé de la couleur LED.":::
4. Retour’écran d’accueil et vérifiez que la couleur LED de l’état occupé est mise à jour. Si l’espace de réunion est actuellement disponible, essayez de planifier une réunion test pour vérifier la modification de la couleur de LED pour l’état occupé.

## <a name="frequently-asked-questions"></a>Questions fréquentes (FAQ)

Trouvez des réponses aux questions fréquemment posées sur les Teams panneaux.

**À quelle distance puis-je voir les détails de la planification d’un espace de réunion ?**  
Dans la  vignette Calendrier à venir (en bas à droite) de l’écran d’accueil, vous pouvez voir les détails de planification d’un espace de réunion pour 24 heures à partir de l’heure actuelle.

**Puis-je réserver un espace de réunion pour une heure ultérieure à partir du périphérique Teams panneaux ?**  
Non, vous ne pouvez pas réserver d’espace de réunion pour une heure ultérieure à partir de panneaux. L’heure de début est toujours l’heure actuelle pour une réunion ad hoc prévue à partir de panneaux.

**Combien de temps puis-je réserver un espace de réunion disponible pour une réunion ad hoc ?**  
Vous pouvez réserver un espace de réunion disponible à partir de l’heure actuelle jusqu’à l’heure de la prochaine réunion prévue, ou jusqu’à 24 heures à partir de votre heure actuelle, selon la date antérieure. Par exemple, si l’heure actuelle est 10 h et que l’heure de début de la prochaine réunion est de 14 h, vous pouvez réserver l’espace de réunion de 10 h à 14 h.
