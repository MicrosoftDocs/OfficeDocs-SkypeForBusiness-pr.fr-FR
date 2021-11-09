---
title: 'Skype Entreprise Server : configurer une trunk sans contournement de média'
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
ms.assetid: 3422e93e-7bd2-4470-968c-dc38345b18ca
description: 'Résumé : Configurez une trunk sans la déviation du média activée pour Skype Entreprise Server.'
ms.openlocfilehash: bccc88e442532ebf9a2c503fa851965447eb1e85
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60839116"
---
# <a name="skype-for-business-server-configure-a-trunk-without-media-bypass"></a>Skype Entreprise Server : configurer une trunk sans contournement de média

**Résumé :** Configurez une trunk sans déviation du média activée pour Skype Entreprise Server.

Pour configurer une jonction sur laquelle le contournement de média est désactivé, procédez comme suit. Si vous souhaitez configurer une trunk avec la déviation du média activée, voir [Configure a trunk with media bypass in Skype Entreprise Server](configure-trunk-with-media-bypass.md).

Une configuration de jonction, comme décrit plus bas, regroupe un ensemble de paramètres appliqués aux jonctions affectées à cette configuration de jonction. Une configuration de jonction spécifique peut s’étendre au niveau global (à toutes les jonctions qui ne disposent plus d’une configuration de site ou de pool spécifique) ou au niveau d’un site ou d’un pool. La configuration de jonction au niveau du pool est utilisée pour étendre une configuration de jonction spécifique à une jonction unique.

### <a name="to-configure-a-trunk-without-media-bypass"></a>Pour configurer une jonction sans contournement de média

1. Ouvrez Skype Entreprise Server panneau de contrôle.

2. Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Configuration de la jonction**.

3. Dans la page **Configuration de la jonction**, configurez une jonction à l’aide de l’une des méthodes suivantes :

   - Double-cliquez sur une jonction existante (par exemple, la jonction **Global**) pour afficher la boîte de dialogue **Modifier la configuration de la jonction**.

   - Cliquez sur **Nouvelle**, puis sélectionnez l’étendue de la nouvelle configuration de jonction :

   - **Site trunk:** Choose the site for this trunk configuration in **Select a Site,** and then click **OK**. Notez que si une configuration de trunk a déjà été créée pour un site, le site n’apparaît pas dans **Sélectionner un site.** Cette configuration de la trunk sera appliquée à toutes les trunks du site.

   - **Pool trunk**: Choose the name of the trunk that this trunk configuration applies to in **Select a Service** and click **OK**. Cette trunk peut être la racine ou toute autre trunks supplémentaire définie dans le Générateur de topologie. Notez que si une configuration de trunk a déjà été créée pour une trunk spécifique, la trunk n’apparaît pas dans **Select a Service**.

     > [!NOTE]
     > Une fois que vous avez sélectionné l’étendue de la configuration de jonction, elle n’est plus modifiable. > Le **champ Nom** est pré-rempli avec le nom du site ou du service associé à la configuration de la trunk et ne peut pas être modifié.

4. Sélectionnez l’une des options de **Niveau de prise en charge du chiffrement** :

   - **Obligatoire**: le chiffrement SRTP (Secure Realtime Transport Protocol) doit être utilisé pour protéger le trafic entre le serveur de médiation et la passerelle ou le PBX (Private Branch eXchange).

   - **Facultatif** : le chiffrement SRTP sera utilisé s’il est pris en charge par le fournisseur de services ou le fabricant.

   - **Non pris en charge** : le chiffrement SRTP n’étant pas pris en charge pas le fournisseur de services ou le fabricant, il ne peut pas être utilisé.

5. Assurez-vous que la case à cocher **Activer le contournement de média** est désactivée.

6. Cochez la case Traitement multimédia centralisé s’il existe un point de terminaison multimédia connu (par exemple, une passerelle PSTN où la terminaison multimédia possède la même adresse IP que la terminaison de signalisation).  Désactivez cette case à cocher si la jonction ne comporte pas de point de terminaison multimédia connu.

7. Si l’homologue de la passerelle prend en charge la réception de demandes SIP REFER à partir du serveur de médiation, activez la case à cocher Activer l’envoi pour **la** passerelle.

8. (Facultatif) Pour permettre le routage interjonction, associez et configurez les enregistrements d’utilisation PSTN à la configuration de cette jonction. Les utilisations PSTN associées à cette configuration de Skype Entreprise Server sont appliquées pour tous les appels entrants via la Skype Entreprise Server point de terminaison. Pour gérer les enregistrements d’utilisation PSTN associés à une configuration de jonction, utilisez l’une des méthodes suivantes :

   - Pour sélectionner un ou plusieurs enregistrements dans une liste de tous les enregistrements d’utilisation PSTN disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner.** Sélectionnez les enregistrements à associer à cette configuration de jonction, puis cliquez sur **OK**.

   - Pour supprimer un enregistrement d’utilisation PSTN de cette configuration de jonction, sélectionnez l’enregistrement, puis cliquez sur **Supprimer**.

   - Pour définir un nouvel enregistrement d’utilisation PSTN et l’associer à cette configuration de jonction, procédez comme suit :

     a. Cliquez sur **Nouveau**.

     b. Dans le champ **Nom**, indiquez un nom descriptif unique pour l’enregistrement.

     > [!NOTE]
     > Le nom de l’enregistrement d’utilisation PSTN doit être unique dans le déploiement Voix Entreprise. Une fois que l’enregistrement est enregistré, le champ **Nom** ne peut plus être modifié.

     c. Utilisez l’une des méthodes suivantes pour associer et configurer les itinéraires pour cet enregistrement d’utilisation PSTN :

     - Pour sélectionner un ou plusieurs itinéraires dans la liste de tous les itinéraires disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner.** Sélectionnez les itinéraires que vous voulez associer à cet enregistrement d’utilisation PSTN, puis cliquez sur **OK**.

     - Pour supprimer un itinéraire de l’enregistrement d’utilisation PSTN, sélectionnez l’itinéraire et cliquez sur **Supprimer**.

     - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation PSTN, cliquez sur **Nouveau**. Pour plus d’informations, [voir Créer ou modifier un itinéraire de](create-or-modify-a-voice-route.md)voix dans Skype Entreprise .

     - Pour modifier un itinéraire associé à cet enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**.

     d. Cliquez sur **OK**.

   - Pour modifier un enregistrement d’utilisation PSTN déjà associé à cette configuration de jonction, procédez comme suit :

     a. Sélectionnez l’enregistrement d’utilisation PSTN que vous voulez modifier, puis cliquez sur **Afficher les détails**.

     b. Utilisez l’une des méthodes suivantes pour associer et configurer les itinéraires pour cet enregistrement d’utilisation PSTN :

     - Pour sélectionner un ou plusieurs itinéraires dans la liste de tous les itinéraires disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner.** Sélectionnez les itinéraires que vous voulez associer à cet enregistrement d’utilisation PSTN, puis cliquez sur **OK**.

     - Pour supprimer un itinéraire de l’enregistrement d’utilisation PSTN, sélectionnez l’itinéraire et cliquez sur **Supprimer**.

     - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation PSTN, cliquez sur **Nouveau**. Pour plus d’informations, [voir Créer ou modifier un itinéraire de](create-or-modify-a-voice-route.md)voix dans Skype Entreprise .

     - Pour modifier un itinéraire associé à cet enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**.

     c. Cliquez sur **OK**.

     > [!IMPORTANT]
     > Il est important d’associer les enregistrements d’utilisation PSTN en fonction de l’homologue du serveur de médiation associé à la trunk en cours de configuration. Si l’homologue du serveur de médiation est une passerelle PSTN ou un contrôleur de frontière de session (SBC), il est vivement recommandé que la configuration de la connexion ne soit pas associée à un enregistrement d’utilisation PSTN qui approvisionnement vers une destination PSTN ou tout autre système en aval connecté via Skype Entreprise Server.

9. Organisez les enregistrements d’utilisation PSTN pour obtenir des performances optimales. Pour modifier la position d’un enregistrement dans la liste, sélectionnez l’enregistrement d’utilisation PSTN, puis cliquez sur les flèches vers le haut ou vers le bas.

    > [!IMPORTANT]
    > L’ordre des enregistrements d’utilisation PSTN dans la liste de la configuration de jonction a son importance. Skype Entreprise Server la liste de haut en bas.

10. **Activer l’accrochage RTP** doit être sélectionné pour activer la déviation du trafic multimédia pour les clients se trouvant derrière une NAT ou un pare-feu et un contrôleur SBC prenant en charge l’accrochage.

11. **Activez l’historique des** appels de transmission pour permettre l’envoi d’informations d’historique des appels à l’homologue de passerelle du serveur de médiation.

12. **Activez le forward P-Asserted-Identity** pour que les informations d’origine de l’appel PAI soient transmis entre le serveur de médiation et le côté passerelle (et vice versa), le cas contraire.

13. **Activer le minuteur de basculement de routage de trafic sortant** doit être sélectionné pour permettre un basculement rapide. La passerelle associée à cette jonction peut informer dans les 10 secondes du traitement de l’appel sortant. Le réroutage vers une autre ligne se produit si cette notification n’est pas reçue par le serveur de médiation. Sur des réseaux avec une latence qui peut retarder le temps de réponse ou si la passerelle prend plus de 10 secondes à répondre, le basculement rapide doit être désactivé.

14. (Facultatif) Associez et configurez les **règles de traduction du numéro d’appel** pour la jonction. Ces règles de traduction s’appliquent au numéro appelant pour les appels sortants

    - Pour choisir une ou plusieurs règles dans une liste de toutes les règles de traduction disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner.** Dans **Sélectionner les règles de traduction**, cliquez sur les règles à associer à la jonction, puis cliquez sur **OK**.

    - Si vous voulez définir une nouvelle règle de traduction et l’associer à la jonction, cliquez sur **Nouvelle**. Pour plus d’informations sur les règles de traduction, voir Règles de [traduction dans Skype Entreprise Server](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md).

    - Pour modifier une règle de traduction associée à une jonction, cliquez sur son nom, puis sur **Afficher les détails**.

    - Pour copier une règle de traduction existante qui servira de point de départ à la définition d’une nouvelle règle, cliquez sur son nom, sur **Copier**, puis sur **Coller**.

    - Pour supprimer une règle de traduction d’une jonction, sélectionnez son nom, puis cliquez sur **Supprimer**.

      > [!CAUTION]
      > N’associez pas de règles de traduction à une configuration de jonction si vous avez configuré les règles de traduction sur l’homologue de jonction associé, car les deux règles risqueraient d’entrer en conflit.

15. (Facultatif) Associez et configurez les **règles de traduction de numéro appelé** pour la jonction. Les règles de traduction s’appliquent au numéro appelé dans un appel sortant.

    - Pour choisir une ou plusieurs règles dans une liste de toutes les règles de traduction disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner.** Dans **Sélectionner les règles de traduction**, cliquez sur les règles à associer à la jonction, puis cliquez sur **OK**.

    - Si vous voulez définir une nouvelle règle de traduction et l’associer à la jonction, cliquez sur **Nouvelle**. Pour plus d’informations sur les règles de traduction, voir Règles de [traduction dans Skype Entreprise Server](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md).

    - Pour modifier une règle de traduction associée à une jonction, cliquez sur son nom, puis sur **Afficher les détails**.

    - Pour copier une règle de traduction existante qui servira de point de départ à la définition d’une nouvelle règle, cliquez sur son nom, sur **Copier**, puis sur **Coller**.

    - Pour supprimer une règle de traduction d’une jonction, sélectionnez son nom, puis cliquez sur **Supprimer**.

      > [!CAUTION]
      > N’associez pas de règles de traduction à une configuration de jonction si vous avez configuré les règles de traduction sur l’homologue de jonction associé, car les deux règles risqueraient d’entrer en conflit.

16. Assurez-vous que les règles de traduction de la trunk sont organisées dans l’ordre correct. Pour modifier la position d’une règle dans la liste, mettez en surbrillez le nom de la règle, puis cliquez sur la flèche vers le haut ou vers le bas.

    > [!IMPORTANT]
    > Skype Entreprise Server parcourt la liste des règles de traduction de haut en bas et utilise la première règle qui correspond au numéro composé. Si vous configurez une jonction de sorte qu’un numéro composé corresponde à plusieurs règles de traduction, assurez-vous que les règles les plus restrictives apparaissent avant les règles les moins restrictives. Par exemple, si vous avez inclus une règle de traduction qui correspond à un numéro à 11 chiffres et une règle de traduction qui ne correspond qu’à des  numéros à 11 chiffres qui commencent par +1425, assurez-vous que la règle qui correspond à un numéro à 11 chiffres est triée sous la règle la plus restrictive.

17. Lorsque vous avez terminé de configurer la jonction, cliquez sur **OK**.

18. Dans la page **Configuration de la jonction**, cliquez sur **Valider**, puis sur **Valider tout**.

    > [!NOTE]
    > À chaque fois que vous créez ou modifiez une configuration de jonction, vous devez exécuter la commande **Valider tout** pour publier la modification de la configuration. Pour plus d’informations, voir [Publish pending changes to the voice routing configuration in Skype Entreprise](voice-route-config-changes.md) in the Operations documentation.

## <a name="see-also"></a>Voir aussi

[Configurer une trunk avec déviation du média dans Skype Entreprise Server](configure-trunk-with-media-bypass.md)

[Définition des règles de traduction](/previous-versions/office/lync-server-2013/lync-server-2013-defining-translation-rules)