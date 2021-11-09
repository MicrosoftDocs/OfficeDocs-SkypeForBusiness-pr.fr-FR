---
title: Créer ou modifier un plan de numérotation dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d2fef3d0-7e78-4591-b712-d62ac71d71a5
description: 'Résumé : Découvrez comment créer ou modifier un plan de numérotation à l’aide du Panneau de Skype Entreprise Server de numérotation.'
ms.openlocfilehash: c5c4a819c21708f31fbe0bf4801900143d0d4538
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60864361"
---
# <a name="create-or-modify-a-dial-plan-in-skype-for-business-server"></a>Créer ou modifier un plan de numérotation dans Skype Entreprise Server

**Résumé :** Découvrez comment créer ou modifier un plan de numérotation à l’aide du Panneau de Skype Entreprise Server de numérotation.

### <a name="to-create-a-dial-plan"></a>Pour créer un plan de numérotation

1. Ouvrez Skype Entreprise Server panneau de contrôle.

2. Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Plan de numérotation**.

3. Dans la page **Plan de numérotation**, cliquez sur **Nouveau**, puis sélectionnez une étendue pour le plan de numérotation :

   - **Plan de numérotation de site** s’applique à tout un site, à l’exception des utilisateurs ou des groupes qui sont attribués au plan de numérotation d’un utilisateur. Si vous **sélectionnez Site pour** l’étendue d’un plan de numérotation, vous devez choisir le site dans la boîte de dialogue Sélectionner un **site.** Si un plan de numérotation a déjà été créé pour un site, le site n’apparaît pas dans la boîte de dialogue **Sélectionner un site**.

   - **Plan de numérotation du pool** peut s’appliquer à une passerelle de réseau téléphonique commuté (PSTN) ou à un serveur d’inscriptions. Si vous sélectionnez **Pool** pour l’étendue d’un plan de numérotation, choisissez la passerelle PSTN ou le bureau d’enregistrement dans la boîte de dialogue **Sélectionner un service.** Si un plan de numérotation a déjà été créé pour un service (passerelle PSTN ou serveur d’inscriptions), le service n’apparaît pas dans la liste.

   - **Plan de numérotation de l’utilisateur** peut s’appliquer à des utilisateurs ou des groupes spécifiques.

     > [!NOTE]
     > Vous ne pouvez pas modifier l’étendue du plan de numérotation que vous avez sélectionnée.

4. Si vous créez le plan de numérotation d’un utilisateur, entrez un nom descriptif dans le champ **Nom** de la boîte de dialogue **Nouveau plan de numérotation**. Une fois enregistré, ce nom ne peut pas être modifié.

    > [!NOTE]
    > Pour les plans  de numérotation de site, le champ Nom est prérepxé avec  le nom du site et ne peut pas être modifié.> Pour les plans de numérotation de pool, le champ Nom est prérepxé avec la passerelle PSTN ou le nom du bureau d’enregistrement et ne peut pas être modifié.

5. Le champ **Nom simple** contient déjà le nom qui figure dans le champ **Nom**. Si vous le souhaitez, vous pouvez modifier ce champ pour spécifier un nom qui reflète mieux le site, le service ou l’utilisateur auquel le plan de numérotation s’applique.

   > [!IMPORTANT]
   > Le **nom simple doit** être unique parmi tous les plans de numérotation de votre déploiement. Il ne peut pas comporter plus de 256 caractères Unicode, chacun d’entre eux étant un caractère alphabétique ou  numérique, un tiret (-), un point (.) ou un trait de soulignement (_).> Les caractères non pris en charge incluent des espaces et des caractères réservés tels que définis dans la norme RFC 3966 ( <http://www.ietf.org/rfc/rfc3966.txt> ). Les caractères réservés qui ne **sont pas pris** en charge dans le nom **simple** sont les suivants : > « ; » "/" "?" ":" "@" "&amp;" "=" "+" "$" ","

6. (Facultatif) Dans le champ **Description**, vous pouvez taper des informations descriptives supplémentaires concernant le plan de numérotation.

7. (Facultatif) Si vous souhaitez utiliser ce plan de numérotation comme une région pour des numéros d’accès entrants, spécifiez une **région de conférence rendez-vous**. Si vous ne souhaitez pas utiliser ce plan de numérotation pour des numéros d’accès entrants, laissez ce champ vide.

    > [!NOTE]
    > Les régions de conférence rendez-vous sont nécessaires pour associer des numéros d’accès entrants à un ou plusieurs plans de numérotation.

8. (Facultatif) Dans le champ **Préfixe d’accès externe**, entrez une valeur uniquement si les utilisateurs doivent composer un ou plusieurs préfixes supplémentaires (le 0, par exemple) pour obtenir une ligne externe. Vous pouvez taper un préfixe de quatre caractères au maximum (#, * et 0-9).

    > [!NOTE]
    > Si vous spécifiez un préfixe d’accès externe, il est inutile de créer une nouvelle règle de normalisation.

9. Associez et configurez les règles de normalisation du plan de numérotation comme suit :

    - Pour choisir une ou plusieurs règles dans une liste de toutes les règles de normalisation disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner.** Dans **Sélectionner des règles de normalisation**, sélectionnez les règles que vous voulez associer au plan de numérotation, puis cliquez sur **OK**.

   - Pour définir une nouvelle règle de normalisation et l’associer au plan de numérotation, cliquez sur **Nouveau**. Pour plus d’informations sur la définition d’une nouvelle règle, voir Créer ou modifier une règle de [normalisation dans Skype Entreprise](normalization-rules.md).

   - Pour modifier une règle de normalisation déjà associée au plan de numérotation, mettez en surbrillance le nom de la règle et cliquez sur **Afficher les détails**.

   - Pour copier une règle de normalisation existante et l’utiliser comme base de définition d’une nouvelle règle, mettez en surbrillance le nom de la règle, cliquez sur **Copier**, puis sur **Coller**.

   - Pour supprimer une règle de normalisation du plan de numérotation, mettez en surbrillance le nom de la règle et cliquez sur **Supprimer**.

     > [!NOTE]
     > Chaque plan de numérotation doit être associé à au moins une règle de normalisation. Pour plus d’informations sur la façon de déterminer toutes les règles de normalisation requises par un plan de numérotation, voir [Plan for outbound voice routing in Skype Entreprise Server](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md) in the Planning documentation.

10. Vérifiez que les règles de normalisation du plan de numérotation sont organisées dans l’ordre correct. Pour modifier la position d’une règle dans la liste, mettez en surbrillez le nom de la règle, puis cliquez sur la flèche vers le haut ou vers le bas.

    > [!IMPORTANT]
    > Skype Entreprise Server parcourt la liste des règles de normalisation de haut en bas et utilise la première règle qui correspond au numéro composé. Si vous configurez un plan de numérotation de sorte qu’un numéro composé puisse correspondre à plusieurs règles de normalisation, vérifiez que les règles plus restrictives apparaissent au-dessus des règles moins restrictives. > la règle de normalisation **Conserver** tout le reste^(\d )$ par défaut correspond à n’importe quel nombre à {11} 11 chiffres. Par exemple, si vous ajoutez une règle de normalisation qui correspond à des nombres  à 11 chiffres qui commencent par 1425, assurez-vous que La règle Conserver tout est triée sous la règle la plus restrictive^(1425\d {7} )$.

11. (Facultatif) Entrez un numéro pour tester le plan de numérotation, puis cliquez sur **OK**. Les résultats du test apparaissent sous **Numéro composé à tester**.

12. Cliquez sur **OK**.

13. Dans la page **Plan de numérotation**, cliquez sur **Valider**, puis sur **Valider tout**.

    > [!NOTE]
    > À chaque fois que vous créez un plan de numérotation, vous devez exécuter la commande **Valider tout** pour publier la modification de la configuration. Pour plus d’informations, voir [Publish pending changes to the voice routing configuration in Skype Entreprise](voice-route-config-changes.md) in the Operations documentation.

### <a name="to-modify-a-dial-plan"></a>Pour modifier un plan de numérotation

1. Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus de détails, voir **Déléguer des autorisations de configuration**.

2. Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir Skype Entreprise Server panneau de bord.

3. Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Plan de numérotation**.

4. Dans la page **Plan de numérotation**, double-cliquez sur le nom d’un plan de numérotation.

    > [!NOTE]
    > L’étendue et le nom du plan de numérotation ont été définis lors de la création de ce plan. Ils ne peuvent pas être modifiés.

5. (Facultatif) Dans **Modifier un plan de numérotation**, modifiez le champ **Nom simple**, qui contient déjà le nom qui apparaît dans le champ **Nom**, pour spécifier un nom qui reflète mieux le site, le service ou l’utilisateur auquel le plan de numérotation s’applique.

    > [!IMPORTANT]
    > Le **nom simple doit** être unique parmi tous les plans de numérotation dans le déploiement de Lync Server 2013. Il ne peut pas dépasser 256 caractères Unicode, chacun d’entre eux peut être un caractère alphabétique ou numérique, un trait d’union (-), un point (.), un signe plus (+) ou un trait de soulignement (_).> Les espaces ne sont pas autorisés dans le champ Nom **simple.**

6. (Facultatif) Dans le champ **Description**, entrez des informations descriptives concernant le plan de numérotation.

7. (Facultatif) Si vous souhaitez utiliser ce plan de numérotation comme une région pour des numéros d’accès entrants, spécifiez une **région de conférence rendez-vous**. Si vous ne souhaitez pas utiliser ce plan de numérotation pour des numéros d’accès entrants, laissez ce champ vide.

    > [!NOTE]
    > Les régions de conférence rendez-vous sont nécessaires pour associer des numéros d’accès entrants à un ou plusieurs plans de numérotation.

8. (Facultatif) Dans le champ **Préfixe d’accès externe**, entrez une valeur uniquement si les utilisateurs doivent composer un ou plusieurs préfixes supplémentaires pour obtenir une ligne externe (le 0, par exemple). Vous pouvez taper un préfixe de quatre caractères au maximum (soit #, * et 0-9).

    > [!NOTE]
    > Si vous spécifiez un préfixe d’accès externe, il est inutile de créer une nouvelle règle de normalisation.

9. Associez et configurez les règles de normalisation du plan de numérotation :

   - Pour choisir une ou plusieurs règles dans une liste de toutes les règles de normalisation disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner.** Dans la boîte de dialogue **Sélectionner des règles de normalisation**, sélectionnez les règles que vous voulez associer au plan de numérotation, puis cliquez sur **OK**.

   - Pour définir une nouvelle règle de normalisation et l’associer au plan de numérotation, cliquez sur **Nouveau**. Pour plus d’informations sur la définition d’une nouvelle règle, voir Créer ou modifier une règle de [normalisation dans Skype Entreprise](normalization-rules.md).

   - Pour modifier une règle de normalisation déjà associée au plan de numérotation, mettez en surbrillance le nom de la règle et cliquez sur **Afficher les détails**.

   - Pour copier une règle de normalisation existante et l’utiliser comme base de définition d’une nouvelle règle, mettez en surbrillance le nom de la règle, cliquez sur **Copier**, puis sur **Coller**.

   - Pour supprimer une règle de normalisation du plan de numérotation, mettez en surbrillance le nom de la règle et cliquez sur **Supprimer**.

     > [!NOTE]
     > Chaque plan de numérotation doit être associé à au moins une règle de normalisation. Pour plus d’informations sur la façon de déterminer toutes les règles de normalisation requises par un plan de numérotation, voir [Plan for outbound voice routing in Skype Entreprise Server](../../plan-your-deployment/enterprise-voice-solution/outbound-voice-routing.md) in the Planning documentation.

10. Vérifiez que les règles de normalisation du plan de numérotation sont organisées dans l’ordre correct. Pour modifier la position d’une règle dans la liste, mettez en surbrillez le nom de la règle, puis cliquez sur la flèche vers le haut ou vers le bas.

    > [!IMPORTANT]
    > Skype Entreprise Server parcourt la liste des règles de normalisation de haut en bas et utilise la première règle qui correspond au numéro composé. Si vous configurez un plan de numérotation de sorte qu’un numéro composé puisse correspondre à plusieurs règles de normalisation, vérifiez que les règles plus restrictives apparaissent au-dessus des règles moins restrictives. > la règle de normalisation **Conserver** tout le reste^(\d )$ par défaut correspond à n’importe quel nombre à {11} 11 chiffres. Si, par exemple, vous ajoutez une règle de normalisation qui correspond aux numéros à  11 chiffres qui commencent par 1425, assurez-vous que La règle Conserver tout est triée sous la règle la plus restrictive^(1425\d {7} )$ .

11. (Facultatif) Entrez un numéro pour tester le plan de numérotation, puis cliquez sur **OK**. Les résultats du test apparaissent sous **Numéro composé à tester**.

    > [!NOTE]
    > Vous pouvez enregistrer un plan de numérotation n’ayant pas encore passé le test afin de le reconfigurer ultérieurement. Pour plus d’informations, voir [Testing Voice Routing](/previous-versions/office/lync-server-2013/lync-server-2013-test-voice-routing).

12. Cliquez sur **OK**.

13. Dans la page **Plan de numérotation**, cliquez sur **Valider**, puis sur **Valider tout**.

    > [!NOTE]
    > Chaque fois que vous créez ou modifiez un plan de numérotation, vous devez exécuter la commande **Valider tout** pour publier la modification de la configuration. Pour plus d’informations, voir [Publish pending changes to the voice routing configuration in Skype Entreprise](voice-route-config-changes.md) in the Operations documentation.

## <a name="see-also"></a>Voir aussi

[Publier les modifications en attente de la configuration du routage des Skype Entreprise](voice-route-config-changes.md)