---
title: Créer ou modifier un plan de numérotation dans Skype pour Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d2fef3d0-7e78-4591-b712-d62ac71d71a5
description: 'Résumé : Apprenez à créer ou modifier un plan de numérotation à l’aide de la Skype pour le panneau de configuration serveur Business.'
ms.openlocfilehash: b8f2e2831a611679f74aebcf49bcc24086adef7e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32207516"
---
# <a name="create-or-modify-a-dial-plan-in-skype-for-business-server"></a>Créer ou modifier un plan de numérotation dans Skype pour Business Server

**Résumé :** Découvrez comment créer ou modifier un plan de numérotation à l’aide de la Skype pour le panneau de configuration serveur Business.

### <a name="to-create-a-dial-plan"></a>Pour créer un plan de numérotation

1. Ouvrez le panneau de configuration serveur Business Skype.

2. Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Plan de numérotation**.

3. Dans la page **Plan de numérotation**, cliquez sur **Nouveau**, puis sélectionnez une étendue pour le plan de numérotation :

   - **Plan de numérotation de site** s’applique à tout un site, à l’exception des utilisateurs ou des groupes attribués au plan de numérotation d’un utilisateur. Si vous sélectionnez un **Site** pour l’étendue d’un plan de numérotation, vous devez choisir le site à partir de la boîte de dialogue **Sélectionner un Site** . Si un plan de numérotation a déjà été créé pour un site, le site ne s’affiche pas dans la boîte de dialogue **Sélectionner un site**.

   - **Plan de numérotation du pool** peut s’appliquer à une passerelle de réseau téléphonique commuté (RTC) ou à un serveur d’inscriptions. Si vous sélectionnez un **Pool** pour l’étendue d’un plan de numérotation, choisissez la passerelle PSTN ou un serveur d’inscriptions dans la boîte de dialogue **Sélectionner un Service** . Si un plan de numérotation a déjà été créé pour un service (passerelle RTC ou serveur d’inscriptions), le service ne s’affiche pas dans la liste.

   - **Plan de numérotation de l’utilisateur** peut s’appliquer à des utilisateurs ou des groupes spécifiques.

     > [!NOTE]
     > Vous ne pouvez pas modifier l’étendue du plan de numérotation que vous avez sélectionnée.

4. Si vous créez le plan de numérotation d’un utilisateur, entrez un nom descriptif dans le champ **Nom** de la boîte de dialogue **Nouveau plan de numérotation**. Une fois enregistré, ce nom ne peut pas être modifié.

    > [!NOTE]
    > Pour les plans de numérotation de site, le champ **nom** est prérempli avec le nom du site et ne peut pas être modifié .> pour le pool plans de numérotation, le champ **nom** est prérempli avec la passerelle PSTN ou le nom du serveur d’inscriptions et ne peut pas être modifié.

5. Le champ **Nom simple** contient déjà le nom qui figure dans le champ **Nom**. Si vous le souhaitez, vous pouvez modifier ce champ pour spécifier un nom qui reflète mieux le site, le service ou l’utilisateur auquel le plan de numérotation s’applique.

   > [!IMPORTANT]
   > Le **nom Simple** doit être unique parmi tous les plans de numérotation de votre déploiement. Il ne peut pas dépasser 256 caractères Unicode, chacun d'entre eux peut être un caractère alphabétique ou numérique, un trait d’union (-), un point (.) ou un trait de soulignement (_) .> caractères **non pris en charge** incluent les espaces et les caractères réservés comme défini dans RFC 3966 (<http://www.ietf.org/rfc/rfc3966.txt>). Caractères réservés **non pris en charge** dans le **Nom Simple** sont les suivantes : > « ; » « / » « ? » « : » « @ » «&amp;» « = » « + « « $», » »

6. (Facultatif) Dans le champ **Description**, vous pouvez taper des informations descriptives supplémentaires concernant le plan de numérotation.

7. (Facultatif) Si vous souhaitez utiliser ce plan de numérotation comme une région pour des numéros d’accès entrants, spécifiez une **région de conférence rendez-vous**. Si vous ne souhaitez pas utiliser ce plan de numérotation pour des numéros d’accès entrants, laissez ce champ vide.

    > [!NOTE]
    > Les régions de conférence rendez-vous sont nécessaires pour associer des numéros d’accès entrants à un ou plusieurs plans de numérotation.

8. (Facultatif) Dans le champ **Préfixe d’accès externe**, entrez une valeur uniquement si les utilisateurs doivent composer un ou plusieurs préfixes supplémentaires (le 9, par exemple) pour obtenir une ligne externe. Vous pouvez taper un préfixe de quatre caractères au maximum (#, * et 0-9).

    > [!NOTE]
    > Si vous spécifiez un préfixe d’accès externe, il est inutile de créer une nouvelle règle de normalisation.

9. Associez et configurez les règles de normalisation du plan de numérotation comme suit :

    - Pour choisir une ou plusieurs règles à partir d’une liste de toutes les règles de normalisation sont disponibles dans votre déploiement d’Enterprise Voice, cliquez sur **Sélectionner**. Dans **Sélectionner des règles de normalisation**, sélectionnez les règles que vous voulez associer au plan de numérotation, puis cliquez sur **OK**.

   - Pour définir une nouvelle règle de normalisation et l’associer au plan de numérotation, cliquez sur **Nouveau**. Pour plus d’informations sur la définition d’une nouvelle règle, voir [créer ou modifier une règle de normalisation dans Skype pour les entreprises](normalization-rules.md).

   - Pour modifier une règle de normalisation déjà associée au plan de numérotation, mettez en surbrillance le nom de la règle et cliquez sur **Afficher les détails**.

   - Pour copier une règle de normalisation existante et l’utiliser comme base de définition d’une nouvelle règle, mettez en surbrillance le nom de la règle, cliquez sur **Copier**, puis sur **Coller**.

   - Pour supprimer une règle de normalisation du plan de numérotation, mettez en surbrillance le nom de la règle et cliquez sur **Supprimer**.

     > [!NOTE]
     > Chaque plan de numérotation doit être associé à au moins une règle de normalisation. Pour plus d’informations sur la façon de déterminer toutes les règles de normalisation un numérotation plan nécessite, voir [Plan for vocaux sortants routage dans Skype pour Business Server](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md) dans la documentation de planification.

10. Vérifiez que les règles de normalisation du plan numérotation sont organisées dans l’ordre correct. Pour modifier la position d’une règle dans la liste, mettez en surbrillance le nom de la règle et cliquez sur l’ou flèche vers le bas.

    > [!IMPORTANT]
    > Skype pour Business Server parcourt la liste des règles de normalisation à partir du haut vers le bas et utilise la première règle qui correspond au numéro composé. Si vous configurez un plan de numérotation de sorte qu’un numéro composé puisse correspondre à plusieurs règles de normalisation, vérifiez que les règles plus restrictives s’affichent au-dessus des règles moins restrictives. > la règle de normalisation par défaut **Conserver tous les** ^(\d{11})$ correspond à n’importe quel numéro à 11 chiffres. Par exemple, si vous ajoutez une règle de normalisation qui correspond à 11 chiffres commençant par 1425, assurez-vous que **Tout conserver** est trié sous le plus restrictif ^(1425\d{7}) règle$.

11. (Facultatif) Entrez un numéro pour tester le plan de numérotation, puis cliquez sur **OK**. Les résultats du test s’affichent sous **Numéro composé à tester**.

12. Cliquez sur **OK**.

13. Dans la page **Plan de numérotation**, cliquez sur **Valider**, puis sur **Valider tout**.

    > [!NOTE]
    > À chaque fois que vous créez un plan de numérotation, vous devez exécuter la commande **Valider tout** pour publier la modification de la configuration. Pour plus d’informations, voir [Publier en attente apportées à la configuration de routage voix dans Skype pour les entreprises](voice-route-config-changes.md) dans la documentation des opérations.

### <a name="to-modify-a-dial-plan"></a>Pour modifier un plan de numérotation

1. Ouvrez une session l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, voir **Delegate Setup Permissions**.

2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.

3. Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Plan de numérotation**.

4. Dans la page **Plan de numérotation**, double-cliquez sur le nom d’un plan de numérotation.

    > [!NOTE]
    > L’étendue et le nom du plan de numérotation ont été définis lors de la création de ce plan. Ils ne peuvent pas être modifiés.

5. (Facultatif) Dans **Modifier un plan de numérotation**, modifiez le champ **Nom simple**, qui contient déjà le nom qui s’affiche dans le champ **Nom**, pour spécifier un nom qui reflète mieux le site, le service ou l’utilisateur auquel le plan de numérotation s’applique.

    > [!IMPORTANT]
    > Le **nom Simple** doit être unique parmi tous les plans de numérotation dans le déploiement de Lync Server 2013. Il ne peut pas dépasser 256 caractères Unicode, chacun d'entre eux peut être des caractères alphabétiques ou numériques, un trait d’union (-), un point (.), un signe plus (+) ou un trait de soulignement (_) .> les espaces ne sont pas autorisés dans le champ **nom Simple** .

6. (Facultatif) Dans le champ **Description**, entrez des informations descriptives concernant le plan de numérotation.

7. (Facultatif) Si vous souhaitez utiliser ce plan de numérotation comme une région pour des numéros d’accès entrants, spécifiez une **région de conférence rendez-vous**. Si vous ne souhaitez pas utiliser ce plan de numérotation pour des numéros d’accès entrants, laissez ce champ vide.

    > [!NOTE]
    > Les régions de conférence rendez-vous sont nécessaires pour associer des numéros d’accès entrants à un ou plusieurs plans de numérotation.

8. (Facultatif) Dans le champ **Préfixe d’accès externe**, entrez une valeur uniquement si les utilisateurs doivent composer un ou plusieurs préfixes supplémentaires pour obtenir une ligne externe (le 9, par exemple). Vous pouvez taper un préfixe de quatre caractères au maximum (soit #, * et 0-9).

    > [!NOTE]
    > Si vous spécifiez un préfixe d’accès externe, il est inutile de créer une nouvelle règle de normalisation.

9. Associez et configurez les règles de normalisation du plan de numérotation :

   - Pour choisir une ou plusieurs règles à partir d’une liste de toutes les règles de normalisation sont disponibles dans votre déploiement d’Enterprise Voice, cliquez sur **Sélectionner**. Dans la boîte de dialogue **Sélectionner des règles de normalisation**, sélectionnez les règles que vous voulez associer au plan de numérotation, puis cliquez sur **OK**.

   - Pour définir une nouvelle règle de normalisation et l’associer au plan de numérotation, cliquez sur **Nouveau**. Pour plus d’informations sur la définition d’une nouvelle règle, voir [créer ou modifier une règle de normalisation dans Skype pour les entreprises](normalization-rules.md).

   - Pour modifier une règle de normalisation déjà associée au plan de numérotation, mettez en surbrillance le nom de la règle et cliquez sur **Afficher les détails**.

   - Pour copier une règle de normalisation existante et l’utiliser comme base de définition d’une nouvelle règle, mettez en surbrillance le nom de la règle, cliquez sur **Copier**, puis sur **Coller**.

   - Pour supprimer une règle de normalisation du plan de numérotation, mettez en surbrillance le nom de la règle et cliquez sur **Supprimer**.

     > [!NOTE]
     > Chaque plan de numérotation doit être associé à au moins une règle de normalisation. Pour plus d’informations sur la façon de déterminer toutes les règles de normalisation un numérotation plan nécessite, voir [Plan for vocaux sortants routage dans Skype pour Business Server](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md) dans la documentation de planification.

10. Vérifiez que les règles de normalisation du plan numérotation sont organisées dans l’ordre correct. Pour modifier la position d’une règle dans la liste, mettez en surbrillance le nom de la règle et cliquez sur l’ou flèche vers le bas.

    > [!IMPORTANT]
    > Skype pour Business Server parcourt la liste des règles de normalisation à partir du haut vers le bas et utilise la première règle qui correspond au numéro composé. Si vous configurez un plan de numérotation de sorte qu’un numéro composé puisse correspondre à plusieurs règles de normalisation, vérifiez que les règles plus restrictives s’affichent au-dessus des règles moins restrictives. > la règle de normalisation par défaut **Conserver tous les** ^(\d{11})$ correspond à n’importe quel numéro à 11 chiffres. Si, par exemple, vous ajoutez une règle de normalisation qui correspond à 11 chiffres commençant par 1425, assurez-vous que **Tout conserver** est trié sous le plus restrictif ^(1425\d{7}) règle$.

11. (Facultatif) Entrez un numéro pour tester le plan de numérotation, puis cliquez sur **OK**. Les résultats du test s’affichent sous **Numéro composé à tester**.

    > [!NOTE]
    > Vous pouvez enregistrer un plan de numérotation n’ayant pas encore passé le test afin de le reconfigurer ultérieurement. Pour plus d’informations, reportez-vous à [Testing Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx).

12. Cliquez sur **OK**.

13. Dans la page **Plan de numérotation**, cliquez sur **Valider**, puis sur **Valider tout**.

    > [!NOTE]
    > Chaque fois que vous créez ou modifiez un plan de numérotation, vous devez exécuter la commande **Valider tout** pour publier la modification de la configuration. Pour plus d’informations, voir [Publier en attente apportées à la configuration de routage voix dans Skype pour les entreprises](voice-route-config-changes.md) dans la documentation des opérations.

## <a name="see-also"></a>Voir aussi

[Publier des modifications en attente de la configuration de routage voix dans Skype pour les entreprises](voice-route-config-changes.md)

