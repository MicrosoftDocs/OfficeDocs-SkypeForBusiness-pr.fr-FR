---
title: Configurer une jonction avec contournement de média dans Skype pour Business Server
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
ms.assetid: 99d729ea-5a4c-4ff2-a4a3-93a24368da6d
description: 'Résumé : Configurez une jonction avec contournement de média activé pour Skype pour Business Server. Cela vous permet de réduire le nombre de serveurs de médiation, en supposant que votre fournisseur de jonction SIP prend en charge.'
ms.openlocfilehash: 8fc6ed21af9bb78240c338e25538cfb0519d49d5
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23890584"
---
# <a name="configure-a-trunk-with-media-bypass-in-skype-for-business-server"></a>Configurer une jonction avec contournement de média dans Skype pour Business Server

**Résumé :** Configurer une jonction avec contournement de média activé pour Skype pour Business Server. Cela vous permet de réduire le nombre de serveurs de médiation, en supposant que votre fournisseur de jonction SIP prend en charge.

Pour configurer une jonction avec l’option de déviation du trafic multimédia activée, procédez comme suit. Pour configurer une jonction avec contournement de média désactivé, voir [configurer une jonction sans media ignorer dans Skype pour Business Server](configure-trunk-without-media-bypass.md).

Le contournement de média est utile lorsque vous souhaitez réduire le nombre de serveurs de médiation déployés. Pour plus d’informations, voir [Plan for media ignorer dans Skype pour les entreprises](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md)

Nous vous conseillons vivement d’activer la déviation du trafic multimédia. Cependant, avant de l’activer sur une jonction SIP (Session Initiation Protocol), assurez-vous que votre fournisseur de jonctions SIP compétent prend en charge cette option et qu’il peut satisfaire aux exigences d’activation du scénario. Plus précisément, le fournisseur doit avoir les adresses IP des serveurs dans le réseau interne de votre organisation.

> [!NOTE]
> La déviation du trafic multimédia ne fonctionnera pas avec chaque passerelle du réseau téléphonique commuté (RTC), système IP-PBX et SBC (Session Border Controller). Microsoft a testé une série de passerelles RTC et de systèmes SBC avec l’aide de partenaires agréés. Le contournement de média est pris en charge uniquement avec les produits et les versions qui sont répertoriées dans la page de [L’Infrastructure de téléphonie pour Skype pour Business Server](https://docs.microsoft.com/SkypeForBusiness/certification/infra-gateways) .

Une configuration de jonction, décrite ci-dessous, regroupe un ensemble de paramètres appliqués aux jonctions auxquelles cette configuration de jonction est affectée. Une configuration de jonction spécifique peut posséder une étendue globale (applicable à toutes les jonctions qui ne disposent pas d’une configuration de pool ou de site plus spécifique) ou une étendue Site ou Pool. La configuration de jonction au niveau du pool sert à appliquer une configuration de jonction spécifique à une jonction unique.

### <a name="to-configure-a-trunk-with-media-bypass"></a>Pour configurer une jonction avec la déviation du trafic multimédia

1. Ouvrez le panneau de configuration serveur Business Skype

2. Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Configuration de la jonction**.

3. Dans la page **Configuration de la jonction**, configurez une jonction à l’aide de l’une des méthodes suivantes :

   - Double-cliquez sur une jonction existante (par exemple, la jonction **Global**) pour afficher la boîte de dialogue **Modifier la configuration de la jonction**.

   - Cliquez sur **Nouvelle**, puis sélectionnez une étendue pour la nouvelle configuration de jonction :

   - **Jonction de site** : sélectionnez le site de la configuration de jonction dans **Sélectionner un site**, puis cliquez sur **OK**. Notez que si une configuration de jonction a déjà été créée pour un site, ce site ne s’affiche pas dans **Sélectionner un site**. Cette configuration de jonction sera appliquée à toutes les jonctions du site.

   - **Jonction de pool**: choisissez le nom du segment auquel s’applique cette configuration de jonction. Cette jonction peut être la jonction racine ou les jonctions supplémentaires définies dans le Générateur de topologie. Dans **Sélectionner un Service**, cliquez sur **OK**. Notez que si une configuration de tronçon a déjà été créée pour une jonction spécifique, la jonction n’apparaît pas dans la zone **Sélectionner un Service**.

      > [!NOTE]
      > Une fois que l’étendue de la configuration de jonction est sélectionnée, elle ne peut plus être modifiée. > Le champ **nom** est prérempli avec le nom d’associé site de la configuration jonction ou service et ne peut pas être modifié.

4. Spécifiez une valeur dans **Nombre maximal de boîtes de dialogue anticipées prises en charge**. Il s’agit du nombre maximal de réponses dirigées qu’une passerelle RTC, IP-PBX ou qu’un contrôleur SBC (Session Border Controller) d’un fournisseur de services de téléphonie et Internet (ITSP) peut recevoir à une INVITATION envoyée au serveur de médiation. La valeur par défaut est 20.

    > [!NOTE]
    > Avant de modifier cette valeur, consultez votre fournisseur de services ou le fabricant de matériel pour plus d’informations sur les capacités de votre système.

5. Sélectionnez l’une des options de **Niveau de prise en charge du chiffrement** :

   - **Requis** : le chiffrement SRTP (Secure Real-time Transport Protocol) doit être utilisé pour aider à protéger le trafic entre le serveur de médiation et la passerelle ou le système PBX.

   - **Facultatif** : le chiffrement SRTP sera utilisé s’il est pris en charge par le fournisseur de services ou le fabricant.

   - **Non pris en charge** : le chiffrement SRTP n’étant pas pris en charge par le fournisseur de services ou le fabricant, il ne peut pas être utilisé.

6. Activez la case à cocher **Activer la déviation du trafic multimédia** si vous souhaitez que le trafic multimédia contourne le serveur de médiation pour être traité par l’homologue de jonction.

    > [!IMPORTANT]
    > Pour que la déviation du trafic multimédia fonctionne correctement, la passerelle RTC, un IP-PBX ou un contrôleur SBC ITSP doit prendre en charge certaines fonctionnalités. Pour plus d’informations, voir [Plan pour le média de contournement dans Skype pour les entreprises](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).

7. Activez la case à cocher **Traitement multimédia centralisé** s’il existe un point de terminaison multimédia connu (par exemple, une passerelle RTC où la terminaison multimédia possède la même adresse IP que la terminaison de signalisation). Désactivez cette case à cocher si la jonction ne comporte pas de point de terminaison multimédia connu.

8. Si l’homologue de jonction prend en charge la réception de demandes SIP REFER à partir du serveur de médiation, activez la case à cocher **permettre l’envoi de faire référence à la passerelle** .

    > [!NOTE]
    > Si vous désactivez cette option alors que l’option **Activer la déviation du trafic multimédia** est sélectionnée, des paramètres supplémentaires sont requis. Si l’homologue de jonction ne prend pas en charge réception des demandes SIP REFER à partir de la déviation du trafic de serveur de médiation et les médias est activé, vous devez également exécuter l’applet de commande **Set-CsTrunkConfiguration** pour désactiver RTCP pour les appels actifs et en attente pour prendre en charge les conditions adéquates pour le contournement de média. En guise d’alternative, vous pouvez sélectionner **Activer la référence avec un contrôle d’appel tiers** si vous souhaitez que les appels transférés soient soumis à la déviation du trafic multimédia et que la passerelle ne prend pas en charge les demandes SIP (Session Initiation Protocol) REFER.

9. (Facultatif) Pour permettre le routage interjonction, associez et configurez les enregistrements d’utilisation RTC à cette configuration de jonction. Les utilisations PSTN associées à cette configuration de jonction seront appliquées pour tous les appels entrants par le biais de la jonction qui n’est pas provenant d’un Skype pour le point de terminaison Business Server. Pour gérer les enregistrements d’utilisation RTC associés à une configuration de jonction, appliquez l’une des méthodes suivantes :

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

10. Organisez les enregistrements d’utilisation RTC pour obtenir des performances optimales. Pour modifier la position d’un enregistrement dans la liste, sélectionnez l’enregistrement d’utilisation PSTN et cliquez sur l’ou les flèches vers le bas.

    > [!IMPORTANT]
    > L’ordre des enregistrements d’utilisation RTC dans la liste de la configuration de jonction a son importance. Skype pour Business Server parcourt la liste du haut vers le bas.

11. L’option **Activer l’accrochage RTP** doit être sélectionnée pour activer la déviation du trafic multimédia pour les clients situés derrière un pare-feu ou un convertisseur d’adresses réseau (NAT) et un contrôleur SBC qui prend en charge l’accrochage.

12. **Activer l’historique du transfert d’appel** doit être sélectionné pour permettre l’envoi des informations d’historique des appels à l’homologue de passerelle du serveur de médiation.

13. **Activer les données de transfert P-Asserted-Identity** doit être sélectionné pour activer les informations de l’expéditeur P-Asserted-Identity (PAI) appel à transférer entre le côté serveur de médiation et le côté passerelle (et vice versa), lorsque présenter.

14. L’option **Activer le minuteur de basculement de routage de trafic sortant** doit être sélectionnée pour permettre un basculement rapide. La passerelle associée à cette jonction peut avertir dans les 10 secondes du traitement de l’appel sortant. Redirection vers une autre jonction se produit si cette notification n’est pas reçue par le serveur de médiation. Sur les réseaux dont la latence peut retarder le temps de réponse ou si la passerelle met plus de 10 secondes à répondre, le basculement rapide doit être désactivé.

15. (Facultatif) Associez et configurez les **règles de conversion du numéro d’appel** pour la jonction. Ces règles de conversion s’appliquent au numéro appelant pour les appels sortants

   - Pour choisir une ou plusieurs règles à partir d’une liste de toutes les règles de traduction qui sont disponibles dans votre déploiement d’Enterprise Voice, cliquez sur **Sélectionner**. Dans **Sélectionner les règles de conversion**, cliquez sur les règles à associer à la jonction, puis cliquez sur **OK**.

   - Pour définir une nouvelle règle de conversion et l’associer à la jonction, cliquez sur **Nouvelle**. Pour plus d’informations sur les règles de traduction, consultez [règles de traduction dans Skype pour Business Server](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md).

   - Pour modifier une règle de conversion déjà associée à la jonction, cliquez sur le nom de la règle, puis sur **Afficher les détails**.

   - Pour copier une règle de conversion existante à utiliser comme point de départ pour définir une nouvelle règle, sélectionnez le nom de la règle et cliquez sur **Copier**, puis sur **Coller**.

   - Pour supprimer une règle de conversion de la jonction, sélectionnez le nom de la règle et cliquez sur **Supprimer**.

   > [!CAUTION]
   > N’associez pas de règles de conversion à une configuration de jonction si vous avez configuré les règles de conversion sur l’homologue de jonction associé, car les deux règles risquent d’entrer en conflit.

16. (Facultatif) Associez et configurez les **règles de conversion de numéro appelé** pour la jonction. Les règles de conversion s’appliquent au numéro appelé dans un appel sortant.

   - Pour choisir une ou plusieurs règles à partir d’une liste de toutes les règles de traduction qui sont disponibles dans votre déploiement d’Enterprise Voice, cliquez sur **Sélectionner**. Dans **Sélectionner les règles de conversion**, cliquez sur les règles à associer à la jonction, puis cliquez sur **OK**.

   - Pour définir une nouvelle règle de conversion et l’associer à la jonction, cliquez sur **Nouvelle**. Pour plus d’informations sur les règles de traduction, consultez [règles de traduction dans Skype pour Business Server](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md).

   - Pour modifier une règle de conversion déjà associée à la jonction, cliquez sur le nom de la règle, puis sur **Afficher les détails**.

   - Pour copier une règle de conversion existante à utiliser comme point de départ pour définir une nouvelle règle, sélectionnez le nom de la règle et cliquez sur **Copier**, puis sur **Coller**.

   - Pour supprimer une règle de conversion de la jonction, sélectionnez le nom de la règle et cliquez sur **Supprimer**.

   > [!CAUTION]
   > N’associez pas de règles de conversion à une configuration de jonction si vous avez configuré les règles de conversion sur l’homologue de jonction associé, car les deux règles risquent d’entrer en conflit.

17. Assurez-vous que les règles de traduction de la jonction sont organisées dans l’ordre correct. Pour modifier la position d’une règle dans la liste, mettez en surbrillance le nom de la règle et cliquez sur l’ou flèche vers le bas.

    > [!IMPORTANT]
    > Skype pour Business Server parcourt la liste des règles de traduction à partir du haut vers le bas et utilise la première règle qui correspond au numéro composé. Si vous configurez une jonction de sorte qu’un numéro composé corresponde à plusieurs règles de conversion, vérifiez que les règles les plus restrictives s’affichent avant les règles les moins restrictives. Par exemple, si vous avez inclus une règle de traduction qui correspond à n’importe quel numéro à 11 chiffres et une règle de traduction qui établit une correspondance avec uniquement les numéros à 11 chiffres commençant par + 1425, assurez-vous que la règle qui correspond à n’importe quel numéro à 11 chiffres est triée *ci-dessous* plus restrictif règle.

18. Lorsque vous avez fini de configurer la jonction, cliquez sur **OK**.

19. Dans la page **Configuration de la jonction**, cliquez sur **Valider**, puis sur **Tout valider**.

   > [!NOTE]
   > Chaque fois que vous créez ou modifiez une configuration de jonction, vous devez exécuter la commande **Tout valider** pour publier la modification de la configuration. Pour plus d’informations, voir [Publier en attente apportées à la configuration de routage voix dans Skype pour les entreprises](voice-route-config-changes.md) dans la documentation des opérations.

Après avoir configuré la jonction, continuez la configuration multimédia contournement de média en choisissant globales de contournement options, comme décrit dans [déployer le contournement de média dans Skype pour Business Server](deploy-media-bypass.md) dans la documentation de déploiement.
## <a name="see-also"></a>Voir aussi

[Configurer une jonction sans contournement de média dans Skype pour Business Server](configure-trunk-without-media-bypass.md)

[Déployer le contournement de média dans Skype pour Business Server](deploy-media-bypass.md)

[Définition des règles de traduction](https://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)

[Configurer le contournement de média](https://technet.microsoft.com/library/f50a7a13-c6a0-48f1-bee1-e45fa2b2f9b8.aspx)

