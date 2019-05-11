---
title: Configurer une jonction sans contournement de média dans Skype pour Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3422e93e-7bd2-4470-968c-dc38345b18ca
description: 'Résumé : Configurez une jonction sans contournement de média activé pour Skype pour Business Server.'
ms.openlocfilehash: 17341ce2b55fcb893f90467db474954440b43951
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33893034"
---
# <a name="configure-a-trunk-without-media-bypass-in-skype-for-business-server"></a>Configurer une jonction sans contournement de média dans Skype pour Business Server

**Résumé :** Configurer une jonction sans contournement de média activé pour Skype pour Business Server.

Pour configurer une jonction sur laquelle la déviation du trafic multimédia est désactivée, procédez comme suit. Si vous souhaitez configurer une jonction avec contournement de média activé, voir [configurer une jonction avec support de contournement dans Skype pour Business Server](configure-trunk-with-media-bypass.md).

Une configuration de jonction, comme indiqué dans la suite de cette rubrique, regroupe un ensemble de paramètres appliqués aux jonctions affectées à cette configuration de jonction. Une configuration de jonction spécifique peut s’étendre au niveau global (à toutes les jonctions qui ne disposent plus d’une configuration de site ou de pool spécifique) ou au niveau d’un site ou d’un pool. La configuration de jonction au niveau du pool est utilisée pour étendre une configuration de jonction spécifique à une jonction unique.

### <a name="to-configure-a-trunk-without-media-bypass"></a>Pour configurer une jonction sans déviation du trafic multimédia

1. Ouvrez le panneau de configuration serveur Business Skype.

2. Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Configuration de la jonction**.

3. Dans la page **Configuration de la jonction**, configurez une jonction à l’aide de l’une des méthodes suivantes :

   - Double-cliquez sur une jonction existante (par exemple, la jonction **Global**) pour afficher la boîte de dialogue **Modifier la configuration de la jonction**.

   - Cliquez sur **Nouvelle**, puis sélectionnez une étendue pour la nouvelle configuration de jonction :

   - **Jonction de site**: choisissez le site pour cette configuration de jonction dans **Sélectionner un Site**, puis cliquez sur **OK**. Notez que si une configuration de tronçon a déjà été créée pour un site, le site n’apparaît pas dans la zone **Sélectionner un Site**. Cette configuration de jonction sera appliquée à toutes les jonctions dans le site.

   - **Jonction de pool**: choisissez le nom du segment auquel s’applique cette configuration de jonction dans **Sélectionner un Service** , cliquez sur **OK**. Cette jonction peut être la jonction racine, ou les jonctions supplémentaires définies dans le Générateur de topologie. Notez que si une configuration de tronçon a déjà été créée pour une jonction spécifique, la jonction n’apparaît pas dans la zone **Sélectionner un Service**.

     > [!NOTE]
     > Une fois que l’étendue de la configuration de jonction est sélectionnée, elle ne peut plus être modifiée. > le champ **nom** est prédéfinie avec le nom d’associé site de la configuration jonction ou service et ne peut pas être modifié.

4. Sélectionnez l’une des options de **Niveau de prise en charge du chiffrement** :

   - **Requis** : le chiffrement SRTP (Secure Real-time Transport Protocol) doit être utilisé pour aider à protéger le trafic entre le serveur de médiation et la passerelle ou le système PBX.

   - **Facultatif** : le chiffrement SRTP sera utilisé s’il est pris en charge par le fournisseur de services ou le fabricant.

   - **Non pris en charge** : le chiffrement SRTP n’étant pas pris en charge par le fournisseur de services ou le fabricant, il ne peut pas être utilisé.

5. Assurez-vous que la case à cocher **Activer la déviation du trafic multimédia** est désactivée.

6. Activez la case à cocher **Traitement multimédia centralisé** si un point de terminaison média connu existe (par exemple, une passerelle RTC sur laquelle la terminaison multimédia possède la même adresse IP que la terminaison de signalisation). Désactivez cette case à cocher si la jonction ne comporte pas de point de terminaison multimédia connu.

7. Si l’homologue de jonction prend en charge la réception de demandes SIP REFER à partir du serveur de médiation, activez la case à cocher **permettre l’envoi de faire référence à la passerelle** .

8. (Facultatif) Pour permettre le routage interjonction, associez et configurez les enregistrements d’utilisation RTC à cette configuration de jonction. Les utilisations PSTN associées à cette configuration de jonction seront appliquées pour tous les appels entrants par le biais de la jonction qui n’est pas provenant d’un Skype pour le point de terminaison Business Server. Pour gérer les enregistrements d’utilisation RTC associés à une configuration de jonction, appliquez l’une des méthodes suivantes :

   - Pour sélectionner un ou plusieurs enregistrements d’une liste de tous les enregistrements d’utilisation PSTN disponibles dans votre déploiement d’Enterprise Voice, cliquez sur **Sélectionner**. Sélectionnez les enregistrements à associer à cette configuration de jonction, puis cliquez sur **OK**.

   - Pour supprimer un enregistrement d’utilisation RTC de cette configuration de jonction, sélectionnez l’enregistrement, puis cliquez sur **Supprimer**.

   - Pour définir un nouvel enregistrement d’utilisation RTC et l’associer à cette configuration de jonction, procédez comme suit :

     a. Cliquez sur **Nouveau**.

     b. Dans le champ **Nom**, indiquez un nom descriptif unique pour l’enregistrement.

     > [!NOTE]
     > Le nom de l’enregistrement d’utilisation RTC doit être unique dans le déploiement Voix Entreprise. Une fois que vous avez enregistré l’enregistrement, vous ne pouvez plus modifier le champ **Nom**.

     c. Pour associer et configurer les itinéraires pour cet enregistrement d’utilisation RTC, appliquez l’une des méthodes suivantes :

     - Pour sélectionner un ou plusieurs itinéraires à partir de la liste de tous les itinéraires disponibles dans votre déploiement d’Enterprise Voice, cliquez sur **Sélectionner**. Sélectionnez les itinéraires à associer à cet enregistrement d’utilisation RTC, puis cliquez sur **OK**.

     - Pour supprimer un itinéraire de l’enregistrement d’utilisation RTC, sélectionnez l’itinéraire et cliquez sur **Supprimer**.

     - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation RTC, cliquez sur **Nouveau**. Pour plus d’informations, voir [créer ou modifier un itinéraire de communications vocales dans Skype pour les entreprises](create-or-modify-a-voice-route.md).

     - Pour modifier un itinéraire associé à cet enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**.

     d. Cliquez sur **OK**.

   - Pour modifier un enregistrement d’utilisation RTC déjà associé à cette configuration de jonction, procédez comme suit :

     a. Sélectionnez l’enregistrement d’utilisation RTC à modifier, puis cliquez sur **Afficher les détails**.

     b. Pour associer et configurer les itinéraires pour cet enregistrement d’utilisation RTC, appliquez l’une des méthodes suivantes :

     - Pour sélectionner un ou plusieurs itinéraires à partir de la liste de tous les itinéraires disponibles dans votre déploiement d’Enterprise Voice, cliquez sur **Sélectionner**. Sélectionnez les itinéraires à associer à cet enregistrement d’utilisation RTC, puis cliquez sur **OK**.

     - Pour supprimer un itinéraire de l’enregistrement d’utilisation RTC, sélectionnez l’itinéraire et cliquez sur **Supprimer**.

     - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation RTC, cliquez sur **Nouveau**. Pour plus d’informations, voir [créer ou modifier un itinéraire de communications vocales dans Skype pour les entreprises](create-or-modify-a-voice-route.md).

     - Pour modifier un itinéraire associé à cet enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**.

     c. Cliquez sur **OK**.

     > [!IMPORTANT]
     > Il est important d’associer des enregistrements d’utilisation PSTN en fonction de l’homologue du serveur de médiation qui est associé à la jonction en cours de configuration. Si l’homologue du serveur de médiation est une passerelle PSTN ou un contrôleur de Session en périphérie (SBC), il est fortement recommandé que la configuration de jonction n’est pas associée à un enregistrement d’utilisation PSTN qui achemine vers une destination PSTN ou tous les autres systèmes en aval connecté via Skype pour un serveur d’entreprise.

9. Organisez les enregistrements d’utilisation RTC pour bénéficier de performances optimales. Pour modifier la position d’un enregistrement dans la liste, sélectionnez l’enregistrement d’utilisation PSTN et cliquez sur l’ou les flèches vers le bas.

    > [!IMPORTANT]
    > L’ordre des enregistrements d’utilisation RTC dans la liste de la configuration de jonction a son importance. Skype pour Business Server parcourt la liste du haut vers le bas.

10. **Activer l’accrochage RTP** doit être sélectionné pour activer la déviation du trafic multimédia pour les clients se trouvant derrière un convertisseur d’adresses réseau (NAT) ou un pare-feu et un contrôleur SBC prenant en charge l’accrochage.

11. **Activer l’historique du transfert d’appel** doit être sélectionné pour permettre l’envoi des informations d’historique des appels à l’homologue de passerelle du serveur de médiation.

12. **Activer les données de transfert P-Asserted-Identity** doit être sélectionné pour activer les informations de PAI à transférer entre le côté serveur de médiation et le côté passerelle (et vice versa), lorsque présenter.

13. L’option **Activer le minuteur de basculement de routage de trafic sortant** doit être sélectionnée pour permettre un basculement rapide. La passerelle associée à cette jonction peut avertir dans les 10 secondes du traitement de l’appel sortant. Redirection vers une autre jonction se produit si cette notification n’est pas reçue par le serveur de médiation. Sur les réseaux dont la latence peut retarder le temps de réponse ou si la passerelle met plus de 10 secondes à répondre, le basculement rapide doit être désactivé.

14. (Facultatif) Associez et configurez les **règles de conversion du numéro d’appel** pour la jonction. Ces règles de conversion s’appliquent au numéro appelant pour les appels sortants

    - Pour choisir une ou plusieurs règles à partir d’une liste de toutes les règles de traduction qui sont disponibles dans votre déploiement d’Enterprise Voice, cliquez sur **Sélectionner**. Dans **Sélectionner les règles de conversion**, cliquez sur les règles à associer à la jonction, puis cliquez sur **OK**.

    - Pour définir une nouvelle règle de conversion et l’associer à la jonction, cliquez sur **Nouvelle**. Pour plus d’informations sur les règles de traduction, consultez [règles de traduction dans Skype pour Business Server](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md).

    - Pour modifier une règle de conversion déjà associée à la jonction, sélectionnez le nom de la règle, puis sur **Afficher les détails**.

    - Pour copier une règle de conversion existante à utiliser comme point de départ pour définir une nouvelle règle, sélectionnez le nom de la règle, sur **Copier**, puis sur **Coller**.

    - Pour supprimer une règle de conversion de la jonction, sélectionnez le nom de la règle et cliquez sur **Supprimer**.

      > [!CAUTION]
      > N’associez pas de règles de conversion à une configuration de jonction si vous avez configuré les règles de conversion sur l’homologue de jonction associé, car les deux règles risquent d’entrer en conflit.

15. (Facultatif) Associez et configurez les **règles de conversion de numéro appelé** pour la jonction. Les règles de conversion s’appliquent au numéro appelé dans un appel sortant.

    - Pour choisir une ou plusieurs règles à partir d’une liste de toutes les règles de traduction qui sont disponibles dans votre déploiement d’Enterprise Voice, cliquez sur **Sélectionner**. Dans **Sélectionner les règles de conversion**, cliquez sur les règles à associer à la jonction, puis cliquez sur **OK**.

    - Pour définir une nouvelle règle de conversion et l’associer à la jonction, cliquez sur **Nouvelle**. Pour plus d’informations sur les règles de traduction, consultez [règles de traduction dans Skype pour Business Server](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md).

    - Pour modifier une règle de conversion déjà associée à la jonction, sélectionnez le nom de la règle, puis sur **Afficher les détails**.

    - Pour copier une règle de conversion existante à utiliser comme point de départ pour définir une nouvelle règle, sélectionnez le nom de la règle, sur **Copier**, puis sur **Coller**.

    - Pour supprimer une règle de conversion de la jonction, sélectionnez le nom de la règle et cliquez sur **Supprimer**.

      > [!CAUTION]
      > N’associez pas de règles de conversion à une configuration de jonction si vous avez configuré les règles de conversion sur l’homologue de jonction associé, car les deux règles risquent d’entrer en conflit.

16. Assurez-vous que les règles de traduction de la jonction sont organisées dans l’ordre correct. Pour modifier la position d’une règle dans la liste, mettez en surbrillance le nom de la règle, puis cliquez sur l’ou flèche vers le bas.

    > [!IMPORTANT]
    > Skype pour Business Server parcourt la liste des règles de traduction à partir du haut vers le bas et utilise la première règle qui correspond au numéro composé. Si vous configurez une jonction de sorte qu’un numéro composé corresponde à plusieurs règles de conversion, vérifiez que les règles les plus restrictives s’affichent avant les règles les moins restrictives. Par exemple, si vous avez inclus une règle de traduction qui correspond à n’importe quel numéro à 11 chiffres et une règle de traduction qui établit une correspondance avec uniquement les numéros à 11 chiffres commençant par + 1425, assurez-vous que la règle qui correspond à n’importe quel numéro à 11 chiffres est triée *ci-dessous* plus restrictif règle.

17. Lorsque vous avez fini de configurer la jonction, cliquez sur **OK**.

18. Dans la page **Configuration de la jonction**, cliquez sur **Valider**, puis sur **Tout valider**.

    > [!NOTE]
    > Chaque fois que vous créez ou modifiez une configuration de jonction, vous devez exécuter la commande **Tout valider** pour publier la modification de la configuration. Pour plus d’informations, voir [Publier en attente apportées à la configuration de routage voix dans Skype pour les entreprises](voice-route-config-changes.md) dans la documentation des opérations.

## <a name="see-also"></a>Voir aussi

[Configurer une jonction avec contournement de média dans Skype pour Business Server](configure-trunk-with-media-bypass.md)

[Définition des règles de traduction](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)

