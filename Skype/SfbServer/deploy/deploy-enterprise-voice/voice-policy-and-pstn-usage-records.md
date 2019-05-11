---
title: Créer ou modifier une stratégie de voix et configurer les enregistrements d’utilisation PSTN dans Skype pour les entreprises
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
ms.assetid: e6ff27e0-e2d1-4445-840f-08f738200c20
description: 'Résumé : Créer ou modifier des stratégies de voix et configurer les enregistrements d’utilisation PSTN à l’aide de la Skype pour le panneau de configuration serveur Business.'
ms.openlocfilehash: e3314923c4227a630549dd2fc9cce1600263c4aa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892243"
---
# <a name="create-or-modify-a-voice-policy-and-configure-pstn-usage-records-in-skype-for-business"></a>Créer ou modifier une stratégie de voix et configurer les enregistrements d’utilisation PSTN dans Skype pour les entreprises

**Résumé :** Créer ou modifier des stratégies de voix et configurer des enregistrements d’utilisation PSTN à l’aide de la Skype pour le panneau de configuration serveur Business.

> [!NOTE]
> Chaque stratégie vocale doit être associée à au moins un enregistrement d’utilisation du réseau téléphonique commuté (RTC). Pour voir une liste de tous les enregistrements d’utilisation PSTN disponibles dans votre déploiement d’Enterprise Voice et afficher leurs propriétés, voir [PSTN afficher les enregistrements d’utilisation dans Skype pour les entreprises](view-pstn-usage-records.md).

### <a name="to-create-a-voice-policy"></a>Pour créer une stratégie de voix

1. Ouvrez le panneau de configuration serveur Business Skype.

2. Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Stratégie de voix**.

3. Dans la page **Stratégie de voix**, cliquez sur **Nouveau** puis sélectionnez l’étendue de la nouvelle stratégie :

   - La **stratégie de site** s’applique à l’ensemble d’un site, à l’exception des utilisateurs ou des groupes attribués à une stratégie d’utilisateur. Si vous sélectionnez l’étendue Site pour une stratégie, sélectionnez le site dans la boîte de dialogue **Sélectionner un site**. Si une stratégie de voix a déjà été créée pour un site, le site ne s’affiche pas dans la boîte de dialogue **Sélectionner un site**.

   - Une **stratégie d’utilisateur** peut être appliquée à des utilisateurs ou à des groupes spécifiés.

4. Si l’étendue de la stratégie de voix est Utilisateur, entrez un nom décrivant la stratégie dans le champ **Nom**.

    > [!NOTE]
    > Si l’étendue de la stratégie de voix est Site, le champ **Nom** de la boîte de dialogue **Nouvelle stratégie de voix** est prérempli avec le nom du site et ne peut pas être modifié.

5. (Facultatif) Entrez une description supplémentaire de la stratégie de voix.

6. Activez ou désactivez les cases à cocher ci-dessous pour activer ou désactiver chacune des **fonctionnalités d’appel** pour cette stratégie de voix :

   - **Redirection vers la messagerie vocale** empêche les appels acheminés immédiatement vers le système de messagerie vocale de l’utilisateur téléphone mobile lors de la sonnerie simultanée est configuré et le téléphone est éteint, en dehors de la batterie ou en dehors des limites.

     > [!NOTE]
     > Cette fonctionnalité est uniquement configurable par le biais de la Skype pour Business Server Management Shell

   - **Transfert d’appel** permet aux utilisateurs de transférer des appels vers d’autres téléphones et périphériques clients. Skype pour Business Server fournit une plage beaucoup plue d’options de configuration pour le transfert d’appel. Par exemple, si une entreprise ne souhaite pas autoriser le transfert des appels entrants en externe vers le RTC, un administrateur peut appliquer une stratégie de voix spéciale pour déployer cette restriction. Activée par défaut.

   - **Délégation** permet aux utilisateurs de spécifier d’autres utilisateurs pouvant passer et recevoir des appels à leur place. Dans Skype pour Business Server, un délégué peut configurer sonnerie simultanée qui permet aux appels entrants à son responsable faire sonner tous les objectifs en termes de sonnerie simultanée du délégué. Celui-ci bénéficie ainsi d’une plus grande flexibilité pour répondre aux appels destinés au responsable. Activée par défaut.

   - **Transfert d’appel** permet aux utilisateurs de transférer des appels à d’autres utilisateurs. Activée par défaut.

   - **Parcage d’appel** permet aux utilisateurs de parquer des appels en attente, puis de les reprendre avec un autre téléphone ou client. Cette fonctionnalité est désactivée par défaut.

   - **Sonnerie simultanée** permet de faire sonner les appels entrants sur des téléphones supplémentaires (par exemple, un téléphone portable) ou d’autres périphériques de point de terminaison. Skype pour Business Server fournit une plage beaucoup plue d’options de configuration pour la sonnerie simultanée. Activée par défaut.

   - **Appel d’équipe** permet aux utilisateurs d’une équipe définie de répondre à des appels destinés à d’autres membres de l’équipe. Cette fonctionnalité est activée par défaut.

   - **Reroutage RTC** permet de rerouter les appels des utilisateurs (auxquels cette stratégie est affectée) destinés à d’autres utilisateurs de l’entreprise sur le réseau téléphonique commuté (RTC) si le réseau étendu (WAN) est saturé ou indisponible. Cette fonctionnalité est activée par défaut.

   - **Remplacement de stratégie de bande passante** permet aux administrateurs de remplacer les décisions de stratégie du contrôle d’admission des appels pour un utilisateur particulier. Cette fonctionnalité est désactivée par défaut.

     > [!NOTE]
     > La stratégie ne sera remplacée que pour les appels entrants vers l’utilisateur et non pour les appels sortants passés par l’utilisateur. Une fois la session établie, la consommation de bande passante est enregistrée avec précision. Ce paramètre doit être utilisé avec modération et doit être réservé à des décisions appropriées en matière de contrôle d’admission des appels.

   - **Suivi des appels malveillants** permet aux utilisateurs de consigner des appels malveillants (du type menace) à l’aide de l’interface utilisateur du client, qui signale ensuite ces appels dans les enregistrements des détails des appels (CDR). Cette fonctionnalité est désactivée par défaut.

   - **Busy Options** active ou désactive Busy Options pour la stratégie de voix spécifiée. Busy Options permet aux appels entrants d’être redirigés vers la messagerie vocale ou d’être rejetés avec une tonalité d’occupation lorsque l’utilisateur ciblé par l’appel est au téléphone. Busy Options est une nouvelle stratégie de voix de la mise à jour cumulative de juillet 2016. Cocher la case de ce paramètre active Busy Options, la décocher le désactive. Pour plus d’informations, voir [planifier la disponibilité d’Options de Skype pour Business Server](../../plan-your-deployment/enterprise-voice-solution/busy-options.md) et [installer et configurer les Options de disponibilité pour Skype pour Business Server](install-and-configure-busy-options.md).

7. Pour associer et configurer des enregistrements d’utilisation RTC pour cette stratégie de voix, effectuez l’une des opérations suivantes :

   - Pour sélectionner un ou plusieurs enregistrements dans une liste de tous les enregistrements d’utilisation RTC disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner**. Sélectionnez les enregistrements à associer à cette stratégie de voix, puis cliquez sur **OK**.

   - Pour supprimer un enregistrement d’utilisation RTC de cette stratégie de voix, sélectionnez l’enregistrement et cliquez sur **Supprimer**.

   - Pour définir un nouvel enregistrement d’utilisation RTC et l’associer à cette stratégie de voix, procédez comme suit :

     a. Cliquez sur **Nouveau**.

     b. Dans le champ **Nom**, entrez un nom descriptif unique pour l’enregistrement. Par exemple, vous souhaiterez peut-être créer un namedRedmond d’enregistrement d’utilisation PSTN pour les employés à temps plein à Redmond et namedRedmondTemps un autre pour les employés temporaires.

     > [!NOTE]
     > Le nom de l’enregistrement d’utilisation RTC doit être unique dans le déploiement Voix Entreprise. Une fois que vous avez enregistré l’enregistrement, vous ne pouvez plus modifier le champ **Nom**.

     c. Utilisez l’une des méthodes ci-dessous pour associer et configurer les itinéraires de cet enregistrement d’utilisation RTC :

   - Pour sélectionner un ou plusieurs itinéraires dans la liste de tous les itinéraires disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner**, sélectionnez les itinéraires à associer à cet enregistrement d’utilisation RTC, puis cliquez sur **OK**.

   - Pour supprimer un itinéraire de l’enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Supprimer**.

   - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation RTC, cliquez sur **Nouveau**. Pour plus d’informations, voir [créer ou modifier un itinéraire de communications vocales dans Skype pour les entreprises](create-or-modify-a-voice-route.md).

   - Pour modifier un itinéraire déjà associé à cet enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**.

     d. Cliquez sur **OK**.

   - Pour modifier un enregistrement d’utilisation RTC déjà associé à cette stratégie de voix, procédez comme suit :

     a. Sélectionnez l’enregistrement d’utilisation RTC à modifier, puis cliquez sur **Afficher les détails**.

     b. Utilisez l’une des méthodes ci-dessous pour associer et configurer les itinéraires de cet enregistrement d’utilisation RTC :

   - Pour sélectionner un ou plusieurs itinéraires dans la liste de tous les itinéraires disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner**, sélectionnez les itinéraires à associer à cet enregistrement d’utilisation RTC, puis cliquez sur **OK**.

   - Pour supprimer un itinéraire de cet enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Supprimer**.

   - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation RTC, cliquez sur **Nouveau**. Pour plus d’informations, voir [créer ou modifier un itinéraire de communications vocales dans Skype pour les entreprises](create-or-modify-a-voice-route.md).

   - Pour modifier un itinéraire déjà associé à cet enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**.

     c. Cliquez sur **OK**.

8. Organisez les enregistrements d’utilisation RTC pour obtenir des performances optimales. Pour modifier la position d’un enregistrement dans la liste, mettez en surbrillance le nom de l’enregistrement et cliquez sur la flèche vers le bas.

    > [!IMPORTANT]
    > L’ordre dans le PSTN enregistrements d’utilisation sont répertoriés dans la stratégie de voix est important. Skype pour Business Server parcourt la liste à partir du haut vers le bas. Il est recommandé que vous organisez la liste par fréquence d’utilisation, par exemple : RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.

9. Pour associer et configurer les enregistrements d’utilisation RTC pour cette stratégie de voix, effectuez l’une des opérations suivantes :

   - Pour utiliser les mêmes enregistrements d’utilisation RTC pour le transfert d’appels et la sonnerie simultanée que cette stratégie de voix, sélectionnez l’option **Router à l’aide des utilisations RTC d’appel** dans le menu déroulant.

   - Pour autoriser le transfert d’appel et la sonnerie simultanée à Skype interne pour les utilisateurs professionnels uniquement, sélectionnez l’option **interne Skype pour seulement les utilisateurs professionnels de l’itinéraire de communications** à partir du menu déroulant. Calls will not be forwarded to external PSTN numbers.

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

   - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation RTC, cliquez sur **Nouveau**. Pour plus d’informations, voir [créer ou modifier un itinéraire de communications vocales dans Skype pour les entreprises](create-or-modify-a-voice-route.md).

   - Pour modifier un itinéraire déjà associé à cet enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**.

     d. Cliquez sur **OK**.

   - Pour modifier un enregistrement d’utilisation RTC déjà associé à cette stratégie de voix, procédez comme suit :

     a. Sélectionnez l’enregistrement d’utilisation RTC à modifier, puis cliquez sur **Afficher les détails**.

     b. Utilisez l’une des méthodes ci-dessous pour associer et configurer les itinéraires de cet enregistrement d’utilisation RTC :

   - Pour sélectionner un ou plusieurs itinéraires dans la liste de tous les itinéraires disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner**, sélectionnez les itinéraires à associer à cet enregistrement d’utilisation RTC, puis cliquez sur **OK**.

   - Pour supprimer un itinéraire de cet enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Supprimer**.

   - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation RTC, cliquez sur **Nouveau**. Pour plus d’informations, voir [créer ou modifier un itinéraire de communications vocales dans Skype pour les entreprises](create-or-modify-a-voice-route.md).

   - Pour modifier un itinéraire déjà associé à cet enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**.

     c. Cliquez sur **OK**.

10. (Facultatif) Entrez un numéro pour tester la stratégie de voix, puis cliquez sur **OK**. Les résultats du test s’affichent dans **Numéro converti à tester**.

11. Cliquez sur **OK**.

12. Dans la page **Stratégie de voix**, cliquez sur **Valider**, puis sur **Tout valider**.

    > [!NOTE]
    > Chaque fois que vous créez ou modifiez une stratégie de voix, vous devez exécuter la commande **Tout valider** pour publier la modification de la configuration. Pour plus d’informations, voir [Publier en attente apportées à la configuration de routage voix dans Skype pour les entreprises](voice-route-config-changes.md) dans la documentation des opérations.

13. (Facultatif) Échappement de messagerie vocale détecte qu’un appel a été reçu immédiatement à la messagerie vocale de l’utilisateur téléphone mobile et déconnecte l’appel vers la messagerie vocale de téléphone mobile. Ainsi, l’appel de continuer à sonnerie sur l’utilisateur d’autres points de terminaison octroi à l’utilisateur la possibilité de répondre à l’appel. Pour plus d’informations sur la façon de configurer une stratégie de messagerie vocale, voir [Configure redirection vers la messagerie vocale dans Skype pour les entreprises](configure-voice-mail-escape.md).

### <a name="to-modify-a-voice-policy"></a>Pour modifier une stratégie de voix

1. Ouvrez le panneau de configuration serveur Business Skype.

2. Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Stratégie de voix**.

3. Dans la page **Stratégie de voix**, double-cliquez sur le nom d’une stratégie de voix.

    > [!NOTE]
    > L’étendue et le nom ont été définis lors de la création de la stratégie de voix. Ils ne peuvent pas être modifiés.

4. (Facultatif) Dans **Modifier la stratégie de voix**, entrez d’autres informations décrivant la stratégie de voix.

5. Activez ou désactivez les cases à cocher ci-dessous pour activer ou désactiver chacune des **fonctionnalités d’appel** :

   - **Redirection vers la messagerie vocale** empêche les appels acheminés immédiatement vers le système de messagerie vocale de l’utilisateur téléphone mobile lors de la sonnerie simultanée est configuré et le téléphone est éteint, en dehors de la batterie ou en dehors des limites.

     > [!NOTE]
     > Cette fonctionnalité est uniquement configurable par le biais de la Skype pour Business Server Management Shell

   - **Transfert d’appel** permet aux utilisateurs de transférer des appels vers d’autres téléphones et périphériques clients. Skype pour Business Server fournit une plage beaucoup plue d’options de configuration pour le transfert d’appel. Par exemple, si une entreprise ne souhaite pas autoriser le transfert des appels entrants en externe vers le RTC, un administrateur peut appliquer une stratégie de voix spéciale pour déployer cette restriction. Activée par défaut.

   - **Délégation** permet aux utilisateurs de spécifier d’autres utilisateurs pouvant passer et recevoir des appels à leur place. Dans Skype pour Business Server, un délégué peut configurer sonnerie simultanée qui permet aux appels entrants à son responsable faire sonner tous les objectifs en termes de sonnerie simultanée du délégué. Celui-ci bénéficie ainsi d’une plus grande flexibilité pour répondre aux appels destinés au responsable. Cette fonctionnalité est activée par défaut.

   - **Transfert d’appel** permet aux utilisateurs de transférer des appels à d’autres utilisateurs. Cette fonctionnalité est activée par défaut.

   - **Parcage d’appel** permet aux utilisateurs de parquer des appels en attente, puis de les reprendre avec un autre téléphone ou client. Cette fonctionnalité est désactivée par défaut.

   - **Sonnerie simultanée** permet de faire sonner les appels entrants sur des téléphones supplémentaires (par exemple, un téléphone portable) ou d’autres périphériques de point de terminaison. Skype pour Business Server fournit une plage beaucoup plue d’options de configuration pour la sonnerie simultanée. Activée par défaut.

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

     b. Dans le champ **Nom**, entrez un nom descriptif unique pour l’enregistrement. Par exemple, vous souhaiterez peut-être créer un namedRedmond d’enregistrement d’utilisation PSTN pour les employés à plein temps situés à Redmond et un autre enregistrement namedRedmondTemps pour les employés temporaires.

     > [!NOTE]
     > Le nom de l’enregistrement d’utilisation RTC doit être unique dans le déploiement Voix Entreprise. Une fois que vous avez enregistré l’enregistrement, vous ne pouvez plus modifier le champ **Nom**.

     c. Utilisez l’une des méthodes ci-dessous pour associer et configurer les itinéraires de cet enregistrement d’utilisation RTC :

   - Pour sélectionner un ou plusieurs itinéraires dans la liste de tous les itinéraires disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner**, sélectionnez les itinéraires à associer à cet enregistrement d’utilisation RTC, puis cliquez sur **OK**.

   - Pour supprimer un itinéraire de l’enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Supprimer**.

   - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation RTC, cliquez sur **Nouveau**. Pour plus d’informations, voir [créer ou modifier un itinéraire de communications vocales dans Skype pour les entreprises](create-or-modify-a-voice-route.md).

   - Pour modifier un itinéraire déjà associé à cet enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**.

     d. Cliquez sur **OK**.

   - Pour modifier un enregistrement d’utilisation RTC déjà associé à cette stratégie de voix, procédez comme suit :

     a. Sélectionnez l’enregistrement d’utilisation RTC à modifier, puis cliquez sur **Afficher les détails**.

     b. Utilisez l’une des méthodes ci-dessous pour associer et configurer les itinéraires de cet enregistrement d’utilisation RTC :

   - Pour sélectionner un ou plusieurs itinéraires dans la liste de tous les itinéraires disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner**, sélectionnez les itinéraires à associer à cet enregistrement d’utilisation RTC, puis cliquez sur **OK**.

   - Pour supprimer un itinéraire de cet enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Supprimer**.

   - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation RTC, cliquez sur **Nouveau**. Pour plus d’informations, voir [créer ou modifier un itinéraire de communications vocales dans Skype pour les entreprises](create-or-modify-a-voice-route.md).

   - Pour modifier un itinéraire déjà associé à cet enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**.

     c. Cliquez sur **OK**.

7. Organisez les enregistrements d’utilisation RTC pour obtenir des performances optimales. Pour modifier la position d’un enregistrement dans la liste, mettez en surbrillance le nom de l’enregistrement et cliquez sur la flèche vers le bas.

    > [!NOTE]
    > L’ordre dans le PSTN enregistrements d’utilisation sont répertoriés dans la stratégie de voix est important. Skype pour Business Server parcourt la liste à partir du haut vers le bas. Il est recommandé que vous organisez la liste par fréquence d’utilisation, par exemple : RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.

8. Pour associer et configurer les enregistrements d’utilisation RTC pour cette stratégie de voix, effectuez l’une des opérations suivantes :

   - Pour utiliser les mêmes enregistrements d’utilisation RTC pour le transfert d’appels et la sonnerie simultanée que cette stratégie de voix, sélectionnez l’option **Router à l’aide des utilisations RTC d’appel** dans le menu déroulant.

   - Pour autoriser le transfert d’appel et la sonnerie simultanée à Skype interne pour les utilisateurs professionnels uniquement, sélectionnez **itinéraire à Skype interne pour les utilisateurs professionnels uniquement** à partir du menu déroulant. Calls will not be forwarded to external PSTN numbers.

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

   - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation RTC, cliquez sur **Nouveau**. Pour plus d’informations, voir [créer ou modifier un itinéraire de communications vocales dans Skype pour les entreprises](create-or-modify-a-voice-route.md).

   - Pour modifier un itinéraire déjà associé à cet enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**. Pour plus d’informations, reportez-vous à la rubrique [Modify a Voice Route](https://technet.microsoft.com/library/afc562cc-8807-489b-8850-dbbe1c1ab9f5.aspx) (contenu éventuellement en anglais).

     d. Cliquez sur **OK**.

   - Pour modifier un enregistrement d’utilisation RTC déjà associé à cette stratégie de voix, procédez comme suit :

     a. Sélectionnez l’enregistrement d’utilisation RTC à modifier, puis cliquez sur **Afficher les détails**.

     b. Utilisez l’une des méthodes ci-dessous pour associer et configurer les itinéraires de cet enregistrement d’utilisation RTC :

     - Pour sélectionner un ou plusieurs itinéraires dans la liste de tous les itinéraires disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner**, sélectionnez les itinéraires à associer à cet enregistrement d’utilisation RTC, puis cliquez sur **OK**.

     - Pour supprimer un itinéraire de cet enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Supprimer**.

     - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation RTC, cliquez sur **Nouveau**. Pour plus d’informations, voir [créer ou modifier un itinéraire de communications vocales dans Skype pour les entreprises](create-or-modify-a-voice-route.md).

     - Pour modifier un itinéraire déjà associé à cet enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**. Pour plus d’informations, reportez-vous à la rubrique [Modify a Voice Route](https://technet.microsoft.com/library/afc562cc-8807-489b-8850-dbbe1c1ab9f5.aspx) (contenu éventuellement en anglais).

     c. Cliquez sur **OK**.

9. (Facultatif) Entrez un numéro pour tester la stratégie de voix, puis cliquez sur **OK**. Les résultats du test s’affichent dans **Numéro converti à tester**.

10. Cliquez sur **OK**.

11. Dans la page **Stratégie de voix**, cliquez sur **Valider**, puis sur **Tout valider**.

    > [!NOTE]
    > Chaque fois que vous créez ou modifiez une stratégie de voix, vous devez exécuter la commande **Tout valider** pour publier la modification de la configuration. Pour plus d’informations, voir [Publier en attente apportées à la configuration de routage voix dans Skype pour les entreprises](voice-route-config-changes.md) dans la documentation des opérations.

12. (Facultatif) Échappement de messagerie vocale détecte qu’un appel a été reçu immédiatement à la messagerie vocale de l’utilisateur téléphone mobile et déconnecte l’appel vers la messagerie vocale de téléphone mobile. Ainsi, l’appel de continuer à sonnerie sur l’utilisateur d’autres points de terminaison octroi à l’utilisateur la possibilité de répondre à l’appel. Pour plus d’informations sur la façon de configurer une stratégie de messagerie vocale, voir [Configure redirection vers la messagerie vocale dans Skype pour les entreprises](configure-voice-mail-escape.md).

## <a name="see-also"></a>Voir aussi

[Afficher les enregistrements d’utilisation PSTN dans Skype pour les entreprises](view-pstn-usage-records.md)

[Créer ou modifier un itinéraire de communications vocales dans Skype pour les entreprises](create-or-modify-a-voice-route.md)

[Publier des modifications en attente de la configuration de routage voix dans Skype pour les entreprises](voice-route-config-changes.md)

[Configurer la redirection vers la messagerie vocale dans Skype pour les entreprises](configure-voice-mail-escape.md)

