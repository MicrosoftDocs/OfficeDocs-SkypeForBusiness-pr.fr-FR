---
title: Création ou modification d’une stratégie de voix et configuration des enregistrements d’utilisation RTC dans Skype entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: e6ff27e0-e2d1-4445-840f-08f738200c20
description: 'Résumé: créez ou modifiez les stratégies vocales et configurez les enregistrements d’utilisation PSTN à l’aide du panneau de configuration Skype entreprise Server.'
ms.openlocfilehash: 76ce531eab2eb88b9a62c4bc38aae1e899802084
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239928"
---
# <a name="create-or-modify-a-voice-policy-and-configure-pstn-usage-records-in-skype-for-business"></a>Création ou modification d’une stratégie de voix et configuration des enregistrements d’utilisation RTC dans Skype entreprise

**Résumé:** Créez ou modifiez les stratégies vocales et configurez les enregistrements d’utilisation PSTN à l’aide du panneau de configuration Skype entreprise Server.

> [!NOTE]
> Chaque stratégie vocale doit être associée à au moins un enregistrement d’utilisation du réseau téléphonique commuté (RTC). Pour afficher une liste de tous les enregistrements d’utilisation RTC disponibles dans le déploiement de votre voix entreprise et afficher leurs propriétés, voir [afficher les enregistrements d’utilisation RTC dans Skype entreprise](view-pstn-usage-records.md).

### <a name="to-create-a-voice-policy"></a>Pour créer une stratégie de voix

1. Ouvrez le panneau de configuration Skype entreprise Server.

2. Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Stratégie de voix**.

3. Dans la page **Stratégie de voix**, cliquez sur **Nouveau** puis sélectionnez l’étendue de la nouvelle stratégie :

   - La **stratégie de site** s’applique à l’ensemble d’un site, à l’exception des utilisateurs ou des groupes attribués à une stratégie d’utilisateur. Si vous sélectionnez l’étendue Site pour une stratégie, sélectionnez le site dans la boîte de dialogue **Sélectionner un site**. Si une stratégie de voix a déjà été créée pour un site, le site ne s’affiche pas dans la boîte de dialogue **Sélectionner un site**.

   - Une **stratégie d’utilisateur** peut être appliquée à des utilisateurs ou à des groupes spécifiés.

4. Si l’étendue de la stratégie de voix est Utilisateur, entrez un nom décrivant la stratégie dans le champ **Nom**.

    > [!NOTE]
    > Si l’étendue de la stratégie de voix est Site, le champ **Nom** de la boîte de dialogue **Nouvelle stratégie de voix** est prérempli avec le nom du site et ne peut pas être modifié.

5. (Facultatif) Entrez une description supplémentaire de la stratégie de voix.

6. Activez ou désactivez les cases à cocher ci-dessous pour activer ou désactiver chacune des **fonctionnalités d’appel** pour cette stratégie de voix :

   - La **messagerie vocale** permet d’éviter que les appels soient immédiatement routés vers le système de messagerie vocale de l’utilisateur lors de la configuration de la sonnerie simultanée et que le téléphone est éteint, hors batterie ou en dehors de la plage.

     > [!NOTE]
     > Cette fonctionnalité est configurable uniquement via Skype entreprise Server Management Shell

   - **Transfert d’appel** permet aux utilisateurs de transférer des appels vers d’autres téléphones et périphériques clients. Skype entreprise Server offre une gamme d’options de configuration considérablement plus vastes pour le renvoi d’appel. Par exemple, si une entreprise ne souhaite pas autoriser le transfert des appels entrants en externe vers le RTC, un administrateur peut appliquer une stratégie de voix spéciale pour déployer cette restriction. Activée par défaut.

   - **Délégation** permet aux utilisateurs de spécifier d’autres utilisateurs pouvant passer et recevoir des appels à leur place. Dans Skype entreprise Server, un délégué peut configurer une sonnerie simultanée qui permet aux appels entrants vers son responsable de sonner dans toutes les cibles de sonnerie simultanées du délégué. Celui-ci bénéficie ainsi d’une plus grande flexibilité pour répondre aux appels destinés au responsable. Activée par défaut.

   - **Transfert d’appel** permet aux utilisateurs de transférer des appels à d’autres utilisateurs. Activée par défaut.

   - **Parcage d’appel** permet aux utilisateurs de parquer des appels en attente, puis de les reprendre avec un autre téléphone ou client. Cette fonctionnalité est désactivée par défaut.

   - **Sonnerie simultanée** permet de faire sonner les appels entrants sur des téléphones supplémentaires (par exemple, un téléphone portable) ou d’autres périphériques de point de terminaison. Skype entreprise Server offre une gamme importante d’options de configuration pour les sonneries simultanées. Activée par défaut.

   - **Appel d’équipe** permet aux utilisateurs d’une équipe définie de répondre à des appels destinés à d’autres membres de l’équipe. Cette fonctionnalité est activée par défaut.

   - **Reroutage RTC** permet de rerouter les appels des utilisateurs (auxquels cette stratégie est affectée) destinés à d’autres utilisateurs de l’entreprise sur le réseau téléphonique commuté (RTC) si le réseau étendu (WAN) est saturé ou indisponible. Cette fonctionnalité est activée par défaut.

   - **Remplacement de stratégie de bande passante** permet aux administrateurs de remplacer les décisions de stratégie du contrôle d’admission des appels pour un utilisateur particulier. Cette fonctionnalité est désactivée par défaut.

     > [!NOTE]
     > La stratégie ne sera remplacée que pour les appels entrants vers l’utilisateur et non pour les appels sortants passés par l’utilisateur. Une fois la session établie, la consommation de bande passante est enregistrée avec précision. Ce paramètre doit être utilisé avec modération et doit être réservé à des décisions appropriées en matière de contrôle d’admission des appels.

   - **Suivi des appels malveillants** permet aux utilisateurs de consigner des appels malveillants (du type menace) à l’aide de l’interface utilisateur du client, qui signale ensuite ces appels dans les enregistrements des détails des appels (CDR). Cette fonctionnalité est désactivée par défaut.

   - **Busy Options** active ou désactive Busy Options pour la stratégie de voix spécifiée. Busy Options permet aux appels entrants d’être redirigés vers la messagerie vocale ou d’être rejetés avec une tonalité d’occupation lorsque l’utilisateur ciblé par l’appel est au téléphone. Busy Options est une nouvelle stratégie de voix de la mise à jour cumulative de juillet 2016. Cocher la case de ce paramètre active Busy Options, la décocher le désactive. Pour plus d’informations, reportez-vous à la section [planifier des options de disponibilité de Skype entreprise Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md) et [installer et configurer les options occupées pour Skype entreprise Server](install-and-configure-busy-options.md).

7. Pour associer et configurer des enregistrements d’utilisation RTC pour cette stratégie de voix, effectuez l’une des opérations suivantes :

   - Pour sélectionner un ou plusieurs enregistrements dans une liste de tous les enregistrements d’utilisation RTC disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner**. Sélectionnez les enregistrements à associer à cette stratégie de voix, puis cliquez sur **OK**.

   - Pour supprimer un enregistrement d’utilisation RTC de cette stratégie de voix, sélectionnez l’enregistrement et cliquez sur **Supprimer**.

   - Pour définir un nouvel enregistrement d’utilisation RTC et l’associer à cette stratégie de voix, procédez comme suit :

     a. Cliquez sur **Nouveau**.

     b. Dans le champ **Nom**, entrez un nom descriptif unique pour l’enregistrement. Par exemple, vous pouvez être amené à créer un enregistrement d’utilisation RTC namedRedmond pour les employés à temps plein résidant dans Redmond et un autre namedRedmondTemps pour les employés temporaires.

     > [!NOTE]
     > Le nom de l’enregistrement d’utilisation RTC doit être unique dans le déploiement Voix Entreprise. Une fois que vous avez enregistré l’enregistrement, vous ne pouvez plus modifier le champ **Nom**.

     c. Utilisez l’une des méthodes ci-dessous pour associer et configurer les itinéraires de cet enregistrement d’utilisation RTC :

   - Pour sélectionner un ou plusieurs itinéraires dans la liste de tous les itinéraires disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner**, sélectionnez les itinéraires à associer à cet enregistrement d’utilisation RTC, puis cliquez sur **OK**.

   - Pour supprimer un itinéraire de l’enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Supprimer**.

   - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation RTC, cliquez sur **Nouveau**. Pour plus d’informations, reportez-vous à [créer ou modifier un itinéraire vocal dans Skype entreprise](create-or-modify-a-voice-route.md).

   - Pour modifier un itinéraire déjà associé à cet enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**.

     d. Cliquez sur **OK**.

   - Pour modifier un enregistrement d’utilisation RTC déjà associé à cette stratégie de voix, procédez comme suit :

     a. Sélectionnez l’enregistrement d’utilisation RTC à modifier, puis cliquez sur **Afficher les détails**.

     b. Utilisez l’une des méthodes ci-dessous pour associer et configurer les itinéraires de cet enregistrement d’utilisation RTC :

   - Pour sélectionner un ou plusieurs itinéraires dans la liste de tous les itinéraires disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner**, sélectionnez les itinéraires à associer à cet enregistrement d’utilisation RTC, puis cliquez sur **OK**.

   - Pour supprimer un itinéraire de cet enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Supprimer**.

   - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation RTC, cliquez sur **Nouveau**. Pour plus d’informations, reportez-vous à [créer ou modifier un itinéraire vocal dans Skype entreprise](create-or-modify-a-voice-route.md).

   - Pour modifier un itinéraire déjà associé à cet enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**.

     c. Cliquez sur **OK**.

8. Organisez les enregistrements d’utilisation RTC pour obtenir des performances optimales. Pour modifier la position d’un enregistrement dans la liste, sélectionnez le nom de l’enregistrement, puis cliquez sur la flèche vers le haut ou vers le bas.

    > [!IMPORTANT]
    > L’ordre dans lequel les enregistrements d’utilisation RTC apparaissent dans la stratégie vocale est significatif. Skype entreprise Server parcourt la liste du haut vers le bas. Nous vous recommandons d’organiser la liste en fonction de la fréquence d’utilisation, par exemple: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.

9. Pour associer et configurer les enregistrements d’utilisation RTC pour cette stratégie de voix, effectuez l’une des opérations suivantes :

   - Pour utiliser les mêmes enregistrements d’utilisation RTC pour le transfert d’appels et la sonnerie simultanée que cette stratégie de voix, sélectionnez l’option **Router à l’aide des utilisations RTC d’appel** dans le menu déroulant.

   - Pour autoriser le transfert d’appel et la sonnerie simultanée uniquement vers des utilisateurs Skype entreprise internes, sélectionnez l’option **acheminer vers les utilisateurs Skype entreprise internes uniquement** dans le menu déroulant. Calls will not be forwarded to external PSTN numbers.

   - Pour spécifier des enregistrements d’utilisation RTC pour le transfert d’appels et la sonnerie simultanée différents de ceux utilisés pour cette stratégie de voix, sélectionnez l’option **Router à l’aide d’utilisations RTC personnalisées** dans le menu déroulant. Cette option affiche un contrôle pour sélectionner des enregistrements d’utilisation RTC existants ou créer des enregistrements d’utilisation RTC spécifiquement pour le transfert d’appels et la sonnerie simultanée.

   - Pour sélectionner un ou plusieurs enregistrements dans une liste des enregistrements d’utilisation RTC pour le transfert d’appels et la sonnerie simultanée, cliquez sur **Sélectionner**. Sélectionnez les enregistrements à associer à cette stratégie de transfert d’appels et de sonnerie simultanée, puis cliquez sur **OK**.

   - Pour supprimer un enregistrement d’utilisation RTC de cette stratégie de transfert d’appels et de sonnerie simultanée, sélectionnez l’enregistrement et cliquez sur **Supprimer**.

   - Pour définir un nouvel enregistrement d’utilisation RTC et l’associer à cette stratégie de transfert d’appels et de sonnerie simultanée, procédez comme suit :

     a. Cliquez sur **Nouveau**.

     b. Dans le champ **Nom**, entrez un nom descriptif unique pour l’enregistrement.

     > [!NOTE]
     > Le nom de l’enregistrement d’utilisation RTC doit être unique dans le déploiement Voix Entreprise. Une fois que vous avez enregistré l’enregistrement, vous ne pouvez plus modifier le champ **Nom**.

     c. Utilisez l’une des méthodes ci-dessous pour associer et configurer les itinéraires de cet enregistrement d’utilisation RTC :

   - Pour sélectionner un ou plusieurs itinéraires dans la liste de tous les itinéraires disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner**, sélectionnez les itinéraires à associer à cet enregistrement d’utilisation RTC, puis cliquez sur **OK**.

   - Pour supprimer un itinéraire de l’enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Supprimer**.

   - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation RTC, cliquez sur **Nouveau**. Pour plus d’informations, reportez-vous à [créer ou modifier un itinéraire vocal dans Skype entreprise](create-or-modify-a-voice-route.md).

   - Pour modifier un itinéraire déjà associé à cet enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**.

     d. Cliquez sur **OK**.

   - Pour modifier un enregistrement d’utilisation RTC déjà associé à cette stratégie de voix, procédez comme suit :

     a. Sélectionnez l’enregistrement d’utilisation RTC à modifier, puis cliquez sur **Afficher les détails**.

     b. Utilisez l’une des méthodes ci-dessous pour associer et configurer les itinéraires de cet enregistrement d’utilisation RTC :

   - Pour sélectionner un ou plusieurs itinéraires dans la liste de tous les itinéraires disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner**, sélectionnez les itinéraires à associer à cet enregistrement d’utilisation RTC, puis cliquez sur **OK**.

   - Pour supprimer un itinéraire de cet enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Supprimer**.

   - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation RTC, cliquez sur **Nouveau**. Pour plus d’informations, reportez-vous à [créer ou modifier un itinéraire vocal dans Skype entreprise](create-or-modify-a-voice-route.md).

   - Pour modifier un itinéraire déjà associé à cet enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**.

     c. Cliquez sur **OK**.

10. (Facultatif) Entrez un numéro pour tester la stratégie de voix, puis cliquez sur **OK**. Les résultats du test s’affichent dans **Numéro converti à tester**.

11. Cliquez sur **OK**.

12. Dans la page **Stratégie de voix**, cliquez sur **Valider**, puis sur **Tout valider**.

    > [!NOTE]
    > Chaque fois que vous créez ou modifiez une stratégie de voix, vous devez exécuter la commande **Tout valider** pour publier la modification de la configuration. Pour plus d’informations, reportez-vous [à la rubrique publier des modifications en attente sur la configuration de la messagerie dans Skype entreprise](voice-route-config-changes.md) dans la documentation sur les opérations.

13. Facultatif L’échappement de la boîte vocale détecte qu’un appel a été reçu immédiatement par la messagerie vocale de l’utilisateur, et déconnecte l’appel vers la messagerie vocale du téléphone mobile. Cela permet à l’appel de continuer à sonner sur les autres points de terminaison de l’utilisateur, ce qui donne à l’utilisateur la possibilité de répondre à l’appel. Pour plus d’informations sur la configuration d’une stratégie de messagerie vocale, voir [configurer l’échappement de la messagerie vocale dans Skype entreprise](configure-voice-mail-escape.md).

### <a name="to-modify-a-voice-policy"></a>Pour modifier une stratégie de voix

1. Ouvrez le panneau de configuration Skype entreprise Server.

2. Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Stratégie de voix**.

3. Dans la page **Stratégie de voix**, double-cliquez sur le nom d’une stratégie de voix.

    > [!NOTE]
    > L’étendue et le nom ont été définis lors de la création de la stratégie de voix. Ils ne peuvent pas être modifiés.

4. (Facultatif) Dans **Modifier la stratégie de voix**, entrez d’autres informations décrivant la stratégie de voix.

5. Activez ou désactivez les cases à cocher ci-dessous pour activer ou désactiver chacune des **fonctionnalités d’appel** :

   - La **messagerie vocale** permet d’éviter que les appels soient immédiatement routés vers le système de messagerie vocale de l’utilisateur lors de la configuration de la sonnerie simultanée et que le téléphone est éteint, hors batterie ou en dehors de la plage.

     > [!NOTE]
     > Cette fonctionnalité est configurable uniquement via Skype entreprise Server Management Shell

   - **Transfert d’appel** permet aux utilisateurs de transférer des appels vers d’autres téléphones et périphériques clients. Skype entreprise Server offre une gamme d’options de configuration considérablement plus vastes pour le renvoi d’appel. Par exemple, si une entreprise ne souhaite pas autoriser le transfert des appels entrants en externe vers le RTC, un administrateur peut appliquer une stratégie de voix spéciale pour déployer cette restriction. Activée par défaut.

   - **Délégation** permet aux utilisateurs de spécifier d’autres utilisateurs pouvant passer et recevoir des appels à leur place. Dans Skype entreprise Server, un délégué peut configurer une sonnerie simultanée qui permet aux appels entrants vers son responsable de sonner dans toutes les cibles de sonnerie simultanées du délégué. Celui-ci bénéficie ainsi d’une plus grande flexibilité pour répondre aux appels destinés au responsable. Cette fonctionnalité est activée par défaut.

   - **Transfert d’appel** permet aux utilisateurs de transférer des appels à d’autres utilisateurs. Cette fonctionnalité est activée par défaut.

   - **Parcage d’appel** permet aux utilisateurs de parquer des appels en attente, puis de les reprendre avec un autre téléphone ou client. Cette fonctionnalité est désactivée par défaut.

   - **Sonnerie simultanée** permet de faire sonner les appels entrants sur des téléphones supplémentaires (par exemple, un téléphone portable) ou d’autres périphériques de point de terminaison. Skype entreprise Server offre une gamme importante d’options de configuration pour les sonneries simultanées. Activée par défaut.

   - **Appel d’équipe** permet aux utilisateurs d’une équipe définie de répondre à des appels destinés à d’autres membres de l’équipe. Cette fonctionnalité est activée par défaut.

   - **Reroutage RTC** permet de rerouter les appels des utilisateurs (auxquels cette stratégie est affectée) destinés à d’autres utilisateurs de l’entreprise sur le réseau téléphonique commuté (RTC) si le réseau étendu (WAN) est saturé ou indisponible. Cette fonctionnalité est activée par défaut.

   - **Remplacement de stratégie de bande passante** permet aux administrateurs de remplacer les décisions de stratégie du contrôle d’admission des appels pour un utilisateur particulier. Désactivée par défaut.

     > [!NOTE]
     > La stratégie n’est remplacée que pour les appels entrants vers l’utilisateur et non pour les appels sortants passés par l’utilisateur. Une fois la session établie, la consommation de bande passante est enregistrée avec précision. Ce paramètre doit être utilisé avec modération.

   - **Suivi des appels malveillants** permet aux utilisateurs de consigner des appels malveillants (du type menace) à l’aide de l’interface utilisateur du client, qui signale ensuite ces appels dans les enregistrements des détails des appels (CDR). Cette fonctionnalité est désactivée par défaut.

6. Pour associer et configurer des enregistrements d’utilisation RTC pour cette stratégie de voix, effectuez l’une des opérations suivantes :

   - Pour sélectionner un ou plusieurs enregistrements dans une liste de tous les enregistrements d’utilisation RTC disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner**. Sélectionnez les enregistrements à associer à cette stratégie de voix, puis cliquez sur **OK**.

   - Pour supprimer un enregistrement d’utilisation RTC de cette stratégie de voix, sélectionnez l’enregistrement et cliquez sur **Supprimer**.

   - Pour définir un nouvel enregistrement d’utilisation RTC et l’associer à cette stratégie de voix, procédez comme suit :

     a. Cliquez sur **Nouveau**.

     b. Dans le champ **Nom**, entrez un nom descriptif unique pour l’enregistrement. Par exemple, vous pouvez être amené à créer un enregistrement d’utilisation RTC namedRedmond pour les employés à temps plein situés à Redmond et un autre enregistrement namedRedmondTemps pour les employés temporaires.

     > [!NOTE]
     > Le nom de l’enregistrement d’utilisation RTC doit être unique dans le déploiement Voix Entreprise. Une fois que vous avez enregistré l’enregistrement, vous ne pouvez plus modifier le champ **Nom**.

     c. Utilisez l’une des méthodes ci-dessous pour associer et configurer les itinéraires de cet enregistrement d’utilisation RTC :

   - Pour sélectionner un ou plusieurs itinéraires dans la liste de tous les itinéraires disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner**, sélectionnez les itinéraires à associer à cet enregistrement d’utilisation RTC, puis cliquez sur **OK**.

   - Pour supprimer un itinéraire de l’enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Supprimer**.

   - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation RTC, cliquez sur **Nouveau**. Pour plus d’informations, reportez-vous à [créer ou modifier un itinéraire vocal dans Skype entreprise](create-or-modify-a-voice-route.md).

   - Pour modifier un itinéraire déjà associé à cet enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**.

     d. Cliquez sur **OK**.

   - Pour modifier un enregistrement d’utilisation RTC déjà associé à cette stratégie de voix, procédez comme suit :

     a. Sélectionnez l’enregistrement d’utilisation RTC à modifier, puis cliquez sur **Afficher les détails**.

     b. Utilisez l’une des méthodes ci-dessous pour associer et configurer les itinéraires de cet enregistrement d’utilisation RTC :

   - Pour sélectionner un ou plusieurs itinéraires dans la liste de tous les itinéraires disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner**, sélectionnez les itinéraires à associer à cet enregistrement d’utilisation RTC, puis cliquez sur **OK**.

   - Pour supprimer un itinéraire de cet enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Supprimer**.

   - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation RTC, cliquez sur **Nouveau**. Pour plus d’informations, reportez-vous à [créer ou modifier un itinéraire vocal dans Skype entreprise](create-or-modify-a-voice-route.md).

   - Pour modifier un itinéraire déjà associé à cet enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**.

     c. Cliquez sur **OK**.

7. Organisez les enregistrements d’utilisation RTC pour obtenir des performances optimales. Pour modifier la position d’un enregistrement dans la liste, sélectionnez le nom de l’enregistrement, puis cliquez sur la flèche vers le haut ou vers le bas.

    > [!NOTE]
    > L’ordre dans lequel les enregistrements d’utilisation RTC apparaissent dans la stratégie vocale est significatif. Skype entreprise Server parcourt la liste du haut vers le bas. Nous vous recommandons d’organiser la liste en fonction de la fréquence d’utilisation, par exemple: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.

8. Pour associer et configurer les enregistrements d’utilisation RTC pour cette stratégie de voix, effectuez l’une des opérations suivantes :

   - Pour utiliser les mêmes enregistrements d’utilisation RTC pour le transfert d’appels et la sonnerie simultanée que cette stratégie de voix, sélectionnez l’option **Router à l’aide des utilisations RTC d’appel** dans le menu déroulant.

   - Pour autoriser le transfert d’appel et la sonnerie simultanée uniquement vers des utilisateurs Skype entreprise internes, sélectionnez **diriger vers les utilisateurs Skype entreprise internes uniquement** dans le menu déroulant. Calls will not be forwarded to external PSTN numbers.

   - Pour spécifier des enregistrements d’utilisation RTC pour le transfert d’appel et la sonnerie simultanée différents de ceux utilisés pour cette stratégie de voix, sélectionnez l’option **Routage avec des utilisations RTC personnalisées** dans le menu déroulant. Cette option affiche un contrôle pour sélectionner les enregistrements d’utilisation RTC existants ou créer des enregistrements d’utilisation RTC spécifiquement pour le transfert d’appel et la sonnerie simultanée.

   - Pour sélectionner un ou plusieurs enregistrements dans une liste des enregistrements d’utilisation RTC pour le transfert d’appels et la sonnerie simultanée, cliquez sur **Sélectionner**. Sélectionnez les enregistrements à associer à cette stratégie de transfert d’appels et de sonnerie simultanée, puis cliquez sur **OK**.

   - Pour supprimer un enregistrement d’utilisation RTC de cette stratégie de transfert d’appels et de sonnerie simultanée, sélectionnez l’enregistrement et cliquez sur **Supprimer**.

   - Pour définir un nouvel enregistrement d’utilisation RTC et l’associer à cette stratégie de transfert d’appels et de sonnerie simultanée, procédez comme suit :

     a. Cliquez sur **Nouveau**.

     b. Dans le champ **Nom**, entrez un nom descriptif unique pour l’enregistrement.

     > [!NOTE]
     > Le nom de l’enregistrement d’utilisation RTC doit être unique dans le déploiement Voix Entreprise. Une fois que vous avez enregistré l’enregistrement, vous ne pouvez plus modifier le champ **Nom**.

     c. Utilisez l’une des méthodes ci-dessous pour associer et configurer les itinéraires de cet enregistrement d’utilisation RTC :

   - Pour sélectionner un ou plusieurs itinéraires dans la liste de tous les itinéraires disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner**, sélectionnez les itinéraires à associer à cet enregistrement d’utilisation RTC, puis cliquez sur **OK**.

   - Pour supprimer un itinéraire de l’enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Supprimer**.

   - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation RTC, cliquez sur **Nouveau**. Pour plus d’informations, reportez-vous à [créer ou modifier un itinéraire vocal dans Skype entreprise](create-or-modify-a-voice-route.md).

   - Pour modifier un itinéraire déjà associé à cet enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**. Pour plus d’informations, reportez-vous à la rubrique [Modify a Voice Route](https://technet.microsoft.com/library/afc562cc-8807-489b-8850-dbbe1c1ab9f5.aspx) (contenu éventuellement en anglais).

     d. Cliquez sur **OK**.

   - Pour modifier un enregistrement d’utilisation RTC déjà associé à cette stratégie de voix, procédez comme suit :

     a. Sélectionnez l’enregistrement d’utilisation RTC à modifier, puis cliquez sur **Afficher les détails**.

     b. Utilisez l’une des méthodes ci-dessous pour associer et configurer les itinéraires de cet enregistrement d’utilisation RTC :

     - Pour sélectionner un ou plusieurs itinéraires dans la liste de tous les itinéraires disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner**, sélectionnez les itinéraires à associer à cet enregistrement d’utilisation RTC, puis cliquez sur **OK**.

     - Pour supprimer un itinéraire de cet enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Supprimer**.

     - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation RTC, cliquez sur **Nouveau**. Pour plus d’informations, reportez-vous à [créer ou modifier un itinéraire vocal dans Skype entreprise](create-or-modify-a-voice-route.md).

     - Pour modifier un itinéraire déjà associé à cet enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**. Pour plus d’informations, reportez-vous à la rubrique [Modify a Voice Route](https://technet.microsoft.com/library/afc562cc-8807-489b-8850-dbbe1c1ab9f5.aspx) (contenu éventuellement en anglais).

     c. Cliquez sur **OK**.

9. (Facultatif) Entrez un numéro pour tester la stratégie de voix, puis cliquez sur **OK**. Les résultats du test s’affichent dans **Numéro converti à tester**.

10. Cliquez sur **OK**.

11. Dans la page **Stratégie de voix**, cliquez sur **Valider**, puis sur **Tout valider**.

    > [!NOTE]
    > Chaque fois que vous créez ou modifiez une stratégie de voix, vous devez exécuter la commande **Tout valider** pour publier la modification de la configuration. Pour plus d’informations, reportez-vous [à la rubrique publier des modifications en attente sur la configuration de la messagerie dans Skype entreprise](voice-route-config-changes.md) dans la documentation sur les opérations.

12. Facultatif L’échappement de la boîte vocale détecte qu’un appel a été reçu immédiatement par la messagerie vocale de l’utilisateur, et déconnecte l’appel vers la messagerie vocale du téléphone mobile. Cela permet à l’appel de continuer à sonner sur les autres points de terminaison de l’utilisateur, ce qui donne à l’utilisateur la possibilité de répondre à l’appel. Pour plus d’informations sur la configuration d’une stratégie de messagerie vocale, voir [configurer l’échappement de la messagerie vocale dans Skype entreprise](configure-voice-mail-escape.md).

## <a name="see-also"></a>Voir aussi

[Afficher les enregistrements d’utilisation RTC dans Skype entreprise](view-pstn-usage-records.md)

[Création ou modification d’un itinéraire vocal dans Skype entreprise](create-or-modify-a-voice-route.md)

[Les modifications en attente apportées à la configuration de l’acheminement vocal dans Skype entreprise](voice-route-config-changes.md)

[Configurer l’échappement de la messagerie vocale dans Skype entreprise](configure-voice-mail-escape.md)

