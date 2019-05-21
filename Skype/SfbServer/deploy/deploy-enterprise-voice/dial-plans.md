---
title: Création ou modification d’un plan de numérotation dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d2fef3d0-7e78-4591-b712-d62ac71d71a5
description: 'Résumé: Découvrez comment créer ou modifier un plan de numérotation à l’aide du panneau de configuration Skype entreprise Server.'
ms.openlocfilehash: b2556a6b5a86b895f18db0daf981fd04ea49cda1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34291650"
---
# <a name="create-or-modify-a-dial-plan-in-skype-for-business-server"></a>Création ou modification d’un plan de numérotation dans Skype entreprise Server

**Résumé:** Découvrez comment créer ou modifier un plan de numérotation à l’aide du panneau de configuration Skype entreprise Server.

### <a name="to-create-a-dial-plan"></a>Pour créer un plan de numérotation

1. Ouvrez le panneau de configuration Skype entreprise Server.

2. Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Plan de numérotation**.

3. Dans la page **Plan de numérotation**, cliquez sur **Nouveau**, puis sélectionnez une étendue pour le plan de numérotation :

   - **Plan de numérotation de site** s’applique à tout un site, à l’exception des utilisateurs ou des groupes attribués au plan de numérotation d’un utilisateur. Si vous sélectionnez **site** pour l’étendue d’un plan de numérotation, vous devez choisir le site dans la boîte de dialogue **Sélectionner un site** . Si un plan de numérotation a déjà été créé pour un site, le site ne s’affiche pas dans la boîte de dialogue **Sélectionner un site**.

   - **Plan de numérotation du pool** peut s’appliquer à une passerelle de réseau téléphonique commuté (RTC) ou à un serveur d’inscriptions. Si vous sélectionnez **** l’étendue d’un plan de numérotation, sélectionnez la passerelle PSTN ou le Bureau d’enregistrement dans la boîte de dialogue **Sélectionner un service** . Si un plan de numérotation a déjà été créé pour un service (passerelle RTC ou serveur d’inscriptions), le service ne s’affiche pas dans la liste.

   - **Plan de numérotation de l’utilisateur** peut s’appliquer à des utilisateurs ou des groupes spécifiques.

     > [!NOTE]
     > Vous ne pouvez pas modifier l’étendue du plan de numérotation que vous avez sélectionnée.

4. Si vous créez le plan de numérotation d’un utilisateur, entrez un nom descriptif dans le champ **Nom** de la boîte de dialogue **Nouveau plan de numérotation**. Une fois enregistré, ce nom ne peut pas être modifié.

    > [!NOTE]
    > Pour les plans de numérotation de site, le champ **nom** est prérempli avec le nom du site et ne peut pas être modifié. > pour les plans de numérotation de la liste, le champ **nom** est prérempli avec le nom de la passerelle PSTN ou du Bureau d’enregistrement et ne peut pas être modifié.

5. Le champ **Nom simple** contient déjà le nom qui figure dans le champ **Nom**. Si vous le souhaitez, vous pouvez modifier ce champ pour spécifier un nom qui reflète mieux le site, le service ou l’utilisateur auquel le plan de numérotation s’applique.

   > [!IMPORTANT]
   > Le **nom simple** doit être unique parmi tous les plans de numérotation de votre déploiement. Il ne peut pas contenir plus de 256 caractères Unicode, dont chacun peut être un caractère alphabétique ou numérique, un trait d’Union (-), un point (.) ou un trait de soulignement (_). > caractères **non pris en charge** incluent les espaces<http://www.ietf.org/rfc/rfc3966.txt>et les caractères réservés tels qu’ils sont définis dans RFC 3966 (). Les caractères réservés qui ne sont **pas pris en charge** dans le **nom simple** sont les suivants: > ";" «/» «?» ":" "@&amp;" "" = "" + "" $ "", "

6. (Facultatif) Dans le champ **Description**, vous pouvez taper des informations descriptives supplémentaires concernant le plan de numérotation.

7. (Facultatif) Si vous souhaitez utiliser ce plan de numérotation comme une région pour des numéros d’accès entrants, spécifiez une **région de conférence rendez-vous**. Si vous ne souhaitez pas utiliser ce plan de numérotation pour des numéros d’accès entrants, laissez ce champ vide.

    > [!NOTE]
    > Les régions de conférence rendez-vous sont nécessaires pour associer des numéros d’accès entrants à un ou plusieurs plans de numérotation.

8. (Facultatif) Dans le champ **Préfixe d’accès externe**, entrez une valeur uniquement si les utilisateurs doivent composer un ou plusieurs préfixes supplémentaires (le 9, par exemple) pour obtenir une ligne externe. Vous pouvez taper un préfixe de quatre caractères au maximum (#, * et 0-9).

    > [!NOTE]
    > Si vous spécifiez un préfixe d’accès externe, il est inutile de créer une nouvelle règle de normalisation.

9. Associez et configurez les règles de normalisation du plan de numérotation comme suit :

    - Pour sélectionner une ou plusieurs règles dans la liste de toutes les règles de normalisation disponibles dans votre déploiement voix entreprise, cliquez sur **Sélectionner**. Dans **Sélectionner des règles de normalisation**, sélectionnez les règles que vous voulez associer au plan de numérotation, puis cliquez sur **OK**.

   - Pour définir une nouvelle règle de normalisation et l’associer au plan de numérotation, cliquez sur **Nouveau**. Pour plus d’informations sur la définition d’une nouvelle règle, voir [créer ou modifier une règle de normalisation dans Skype entreprise](normalization-rules.md).

   - Pour modifier une règle de normalisation déjà associée au plan de numérotation, mettez en surbrillance le nom de la règle et cliquez sur **Afficher les détails**.

   - Pour copier une règle de normalisation existante et l’utiliser comme base de définition d’une nouvelle règle, mettez en surbrillance le nom de la règle, cliquez sur **Copier**, puis sur **Coller**.

   - Pour supprimer une règle de normalisation du plan de numérotation, mettez en surbrillance le nom de la règle et cliquez sur **Supprimer**.

     > [!NOTE]
     > Chaque plan de numérotation doit être associé à au moins une règle de normalisation. Pour plus d’informations sur la façon de déterminer toutes les règles de normalisation requises par un plan de numérotation, reportez-vous à la section planification du [routage de la voix sortante dans Skype entreprise Server](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md) dans la documentation de planification.

10. Vérifiez que les règles de normalisation du plan de numérotation sont organisées dans l’ordre approprié. Pour modifier la position d’une règle dans la liste, sélectionnez le nom de la règle, puis cliquez sur la flèche vers le haut ou vers le bas.

    > [!IMPORTANT]
    > Skype entreprise Server parcourt la liste des règles de normalisation du haut vers le bas et utilise la première règle qui correspond au numéro composé. Si vous configurez un plan de numérotation de sorte qu’un numéro composé puisse correspondre à plusieurs règles de normalisation, vérifiez que les règles plus restrictives s’affichent au-dessus des règles moins restrictives. > la règle par défaut **conserver toutes les** règles de normalisation{11}^ (\d) $ correspond à un numéro à 11 chiffres. Par exemple, si vous ajoutez une règle de normalisation qui correspond aux numéros à 11 chiffres commençant par 1425, assurez-vous que l’ensemble de la fonction **conserver tout** est trié sous la{7}règle de ^ (1425 \ p) $ la plus restrictive.

11. (Facultatif) Entrez un numéro pour tester le plan de numérotation, puis cliquez sur **OK**. Les résultats du test s’affichent sous **Numéro composé à tester**.

12. Cliquez sur **OK**.

13. Dans la page **Plan de numérotation**, cliquez sur **Valider**, puis sur **Valider tout**.

    > [!NOTE]
    > À chaque fois que vous créez un plan de numérotation, vous devez exécuter la commande **Valider tout** pour publier la modification de la configuration. Pour plus d’informations, reportez-vous [à la rubrique publier des modifications en attente sur la configuration de la messagerie dans Skype entreprise](voice-route-config-changes.md) dans la documentation sur les opérations.

### <a name="to-modify-a-dial-plan"></a>Pour modifier un plan de numérotation

1. Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, consultez **autorisations de configuration de délégué**.

2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration Skype entreprise Server.

3. Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Plan de numérotation**.

4. Dans la page **Plan de numérotation**, double-cliquez sur le nom d’un plan de numérotation.

    > [!NOTE]
    > L’étendue et le nom du plan de numérotation ont été définis lors de la création de ce plan. Ils ne peuvent pas être modifiés.

5. (Facultatif) Dans **Modifier un plan de numérotation**, modifiez le champ **Nom simple**, qui contient déjà le nom qui s’affiche dans le champ **Nom**, pour spécifier un nom qui reflète mieux le site, le service ou l’utilisateur auquel le plan de numérotation s’applique.

    > [!IMPORTANT]
    > Le **nom simple** doit être unique parmi tous les plans de numérotation dans le déploiement de Lync Server 2013. Il ne peut pas contenir plus de 256 caractères Unicode, dont chacun peut être un caractère alphabétique ou numérique, un trait d’Union (-), un point (.), un signe plus (+) ou un trait de soulignement (_). les **** espaces > ne le sont pas.

6. (Facultatif) Dans le champ **Description**, entrez des informations descriptives concernant le plan de numérotation.

7. (Facultatif) Si vous souhaitez utiliser ce plan de numérotation comme une région pour des numéros d’accès entrants, spécifiez une **région de conférence rendez-vous**. Si vous ne souhaitez pas utiliser ce plan de numérotation pour des numéros d’accès entrants, laissez ce champ vide.

    > [!NOTE]
    > Les régions de conférence rendez-vous sont nécessaires pour associer des numéros d’accès entrants à un ou plusieurs plans de numérotation.

8. (Facultatif) Dans le champ **Préfixe d’accès externe**, entrez une valeur uniquement si les utilisateurs doivent composer un ou plusieurs préfixes supplémentaires pour obtenir une ligne externe (le 9, par exemple). Vous pouvez taper un préfixe de quatre caractères au maximum (soit #, * et 0-9).

    > [!NOTE]
    > Si vous spécifiez un préfixe d’accès externe, il est inutile de créer une nouvelle règle de normalisation.

9. Associez et configurez les règles de normalisation du plan de numérotation :

   - Pour sélectionner une ou plusieurs règles dans la liste de toutes les règles de normalisation disponibles dans votre déploiement voix entreprise, cliquez sur **Sélectionner**. Dans la boîte de dialogue **Sélectionner des règles de normalisation**, sélectionnez les règles que vous voulez associer au plan de numérotation, puis cliquez sur **OK**.

   - Pour définir une nouvelle règle de normalisation et l’associer au plan de numérotation, cliquez sur **Nouveau**. Pour plus d’informations sur la définition d’une nouvelle règle, voir [créer ou modifier une règle de normalisation dans Skype entreprise](normalization-rules.md).

   - Pour modifier une règle de normalisation déjà associée au plan de numérotation, mettez en surbrillance le nom de la règle et cliquez sur **Afficher les détails**.

   - Pour copier une règle de normalisation existante et l’utiliser comme base de définition d’une nouvelle règle, mettez en surbrillance le nom de la règle, cliquez sur **Copier**, puis sur **Coller**.

   - Pour supprimer une règle de normalisation du plan de numérotation, mettez en surbrillance le nom de la règle et cliquez sur **Supprimer**.

     > [!NOTE]
     > Chaque plan de numérotation doit être associé à au moins une règle de normalisation. Pour plus d’informations sur la façon de déterminer toutes les règles de normalisation requises par un plan de numérotation, reportez-vous à la section planification du [routage de la voix sortante dans Skype entreprise Server](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md) dans la documentation de planification.

10. Vérifiez que les règles de normalisation du plan de numérotation sont organisées dans l’ordre approprié. Pour modifier la position d’une règle dans la liste, sélectionnez le nom de la règle, puis cliquez sur la flèche vers le haut ou vers le bas.

    > [!IMPORTANT]
    > Skype entreprise Server parcourt la liste des règles de normalisation du haut vers le bas et utilise la première règle qui correspond au numéro composé. Si vous configurez un plan de numérotation de sorte qu’un numéro composé puisse correspondre à plusieurs règles de normalisation, vérifiez que les règles plus restrictives s’affichent au-dessus des règles moins restrictives. > la règle par défaut **conserver toutes les** règles de normalisation{11}^ (\d) $ correspond à un numéro à 11 chiffres. Par exemple, si vous ajoutez une règle de normalisation qui correspond à des numéros à 11 chiffres commençant par 1425, assurez-vous que la valeur **conserver tout** est triée sous la règle plus{7}restrictive ^ (1425 \ d) $.

11. (Facultatif) Entrez un numéro pour tester le plan de numérotation, puis cliquez sur **OK**. Les résultats du test s’affichent sous **Numéro composé à tester**.

    > [!NOTE]
    > Vous pouvez enregistrer un plan de numérotation n’ayant pas encore passé le test afin de le reconfigurer ultérieurement. Pour plus d’informations, reportez-vous à [Testing Voice Routing](https://technet.microsoft.com/library/d3aae909-fef6-440f-b144-0b62dc82bf5d.aspx).

12. Cliquez sur **OK**.

13. Dans la page **Plan de numérotation**, cliquez sur **Valider**, puis sur **Valider tout**.

    > [!NOTE]
    > Chaque fois que vous créez ou modifiez un plan de numérotation, vous devez exécuter la commande **Valider tout** pour publier la modification de la configuration. Pour plus d’informations, reportez-vous [à la rubrique publier des modifications en attente sur la configuration de la messagerie dans Skype entreprise](voice-route-config-changes.md) dans la documentation sur les opérations.

## <a name="see-also"></a>Voir aussi

[Les modifications en attente apportées à la configuration de l’acheminement vocal dans Skype entreprise](voice-route-config-changes.md)

