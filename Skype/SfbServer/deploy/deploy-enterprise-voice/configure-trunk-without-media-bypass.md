---
title: Configuration d’une jonction sans déviation du trafic multimédia dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 3422e93e-7bd2-4470-968c-dc38345b18ca
description: 'Résumé : Configurer un tronc sans le contournement de média activé pour Skype pour Business Server 2015.'
ms.openlocfilehash: 5e3aa618370d77d9781827dfdfe261f6ed43dd8c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-a-trunk-without-media-bypass-in-skype-for-business-server-2015"></a>Configuration d’une jonction sans déviation du trafic multimédia dans Skype Entreprise Server 2015
 
**Résumé :** Configurer un tronc sans le contournement de média activé pour Skype pour Business Server 2015.
  
Pour configurer une jonction sur laquelle la déviation du trafic multimédia est désactivée, procédez comme suit. Si vous souhaitez configurer un tronc avec activé le contournement de média, consultez [configurer une jonction avec un support ignorer dans Skype pour Business Server 2015](configure-trunk-with-media-bypass.md).
  
Une configuration de jonction, comme indiqué dans la suite de cette rubrique, regroupe un ensemble de paramètres appliqués aux jonctions affectées à cette configuration de jonction. Une configuration de jonction spécifique peut s’étendre au niveau global (à toutes les jonctions qui ne disposent plus d’une configuration de site ou de pool spécifique) ou au niveau d’un site ou d’un pool. La configuration de jonction au niveau du pool est utilisée pour étendre une configuration de jonction spécifique à une jonction unique.
  
### <a name="to-configure-a-trunk-without-media-bypass"></a>Pour configurer une jonction sans déviation du trafic multimédia

1. Ouvrez Skype pour le panneau de configuration de Business Server.
    
2. Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Configuration de la jonction**.
    
3. Dans la page **Configuration de la jonction**, configurez une jonction à l’aide de l’une des méthodes suivantes :
    
   - Double-cliquez sur une jonction existante (par exemple, la jonction **Global**) pour afficher la boîte de dialogue **Modifier la configuration de la jonction**.
    
   - Cliquez sur **Nouvelle**, puis sélectionnez une étendue pour la nouvelle configuration de jonction :
    
   - **Jonction de site**: choisissez le site pour cette configuration de jonction dans **Sélectionner un Site**, puis cliquez sur **OK**. Notez que si une configuration de jonction a déjà été créée pour un site, le site n’apparaît pas dans la zone **Sélectionner un Site**. Cette configuration de jonction s’appliqueront à tous les puits qui y aboutissent dans le site.
    
   - **Jonction de pool**: choisissez le nom du tronc auquel s’applique cette configuration de jonction dans **Sélectionner un Service** et cliquez sur **OK**. Cette jonction peut être le tronc racine ou les trunks supplémentaires définies dans le Générateur de topologies. Notez que si une configuration de jonction a déjà été créée pour une ligne spécifique, le tronc n’apparaît pas dans la zone **Sélectionner un Service**.
    
    > [!NOTE]
    > Une fois que l’étendue de la configuration de jonction est sélectionnée, elle ne peut plus être modifiée. > Le champ **nom** est prédéfinie avec le nom de site associé de la configuration jonction ou de service et ne peut pas être modifié.
  
4. Sélectionnez l’une des options de **Niveau de prise en charge du chiffrement** :
    
   - **Requis** : le chiffrement SRTP (Secure Real-time Transport Protocol) doit être utilisé pour aider à protéger le trafic entre le serveur de médiation et la passerelle ou le système PBX.
    
   - **Facultatif** : le chiffrement SRTP sera utilisé s’il est pris en charge par le fournisseur de services ou le fabricant.
    
   - **Non pris en charge** : le chiffrement SRTP n’étant pas pris en charge par le fournisseur de services ou le fabricant, il ne peut pas être utilisé.
    
5.  Assurez-vous que la case à cocher **Activer la déviation du trafic multimédia** est désactivée.
    
6. Activez la case à cocher **Traitement multimédia centralisé** si un point de terminaison média connu existe (par exemple, une passerelle RTC sur laquelle la terminaison multimédia possède la même adresse IP que la terminaison de signalisation). Désactivez cette case à cocher si la jonction ne comporte pas de point de terminaison multimédia connu.
    
7. Si l’homologue trunk prend en charge la réception SIP demandes à partir du serveur de médiation, activez la case à cocher **Activer l’envoi de faire référence à la passerelle** .
    
8. (Facultatif) Pour permettre le routage interjonction, associez et configurez les enregistrements d’utilisation RTC à cette configuration de jonction. Les utilisations de RTPC associées à cette configuration de jonction seront appliquées pour tous les appels entrants via le trunk qui n’est pas originaires d’un Skype pour point de terminaison de serveur d’entreprise. Pour gérer les enregistrements d’utilisation RTC associés à une configuration de jonction, appliquez l’une des méthodes suivantes :
    
   - Pour sélectionner un ou plusieurs enregistrements à partir d’une liste de tous les enregistrements d’utilisation RTPC disponibles dans votre déploiement de Voix Entreprise, cliquez sur **Sélectionner**. Sélectionnez les enregistrements à associer à cette configuration de jonction, puis cliquez sur **OK**.
    
   - Pour supprimer un enregistrement d’utilisation RTC de cette configuration de jonction, sélectionnez l’enregistrement, puis cliquez sur **Supprimer**.
    
   - Pour définir un nouvel enregistrement d’utilisation RTC et l’associer à cette configuration de jonction, procédez comme suit :
    
     a. Cliquez sur **Nouveau**.
    
     b. Dans le champ **Nom**, indiquez un nom descriptif unique pour l’enregistrement.
    
     > [!NOTE]
     > Le nom de l’enregistrement d’utilisation RTC doit être unique dans le déploiement Voix Entreprise. Une fois que vous avez enregistré l’enregistrement, vous ne pouvez plus modifier le champ **Nom**.
  
     c. Pour associer et configurer les itinéraires pour cet enregistrement d’utilisation RTC, appliquez l’une des méthodes suivantes :
    
     - Pour sélectionner un ou plusieurs itinéraires à partir de la liste de toutes les routes disponibles dans votre déploiement de Voix Entreprise, cliquez sur **Sélectionner**. Sélectionnez les itinéraires à associer à cet enregistrement d’utilisation RTC, puis cliquez sur **OK**. 
    
     - Pour supprimer un itinéraire de l’enregistrement d’utilisation RTC, sélectionnez l’itinéraire et cliquez sur **Supprimer**.
    
     - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation RTC, cliquez sur **Nouveau**. Pour plus d’informations, consultez [créer ou modifier un itinéraire de voix dans Skype pour 2015 de Business](create-or-modify-a-voice-route.md).
    
     - Pour modifier un itinéraire associé à cet enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**.
    
     d. Cliquez sur **OK**.
    
   - Pour modifier un enregistrement d’utilisation RTC déjà associé à cette configuration de jonction, procédez comme suit :
    
    a. Sélectionnez l’enregistrement d’utilisation RTC à modifier, puis cliquez sur **Afficher les détails**.
    
    b. Pour associer et configurer les itinéraires pour cet enregistrement d’utilisation RTC, appliquez l’une des méthodes suivantes :
    
     - Pour sélectionner un ou plusieurs itinéraires à partir de la liste de toutes les routes disponibles dans votre déploiement de Voix Entreprise, cliquez sur **Sélectionner**. Sélectionnez les itinéraires à associer à cet enregistrement d’utilisation RTC, puis cliquez sur **OK**. 
    
     - Pour supprimer un itinéraire de l’enregistrement d’utilisation RTC, sélectionnez l’itinéraire et cliquez sur **Supprimer**.
    
     - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation RTC, cliquez sur **Nouveau**. Pour plus d’informations, consultez [créer ou modifier un itinéraire de voix dans Skype pour 2015 de Business](create-or-modify-a-voice-route.md).
    
     - Pour modifier un itinéraire associé à cet enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**.
    
    c. Cliquez sur **OK**.
    
     > [!IMPORTANT]
     > Il est important d’associer les enregistrements d’utilisation RTPC en fonction de l’homologue de serveur de médiation qui est associé à la jonction en cours de configuration. Si l’homologue de serveur de médiation est une passerelle PSTN ou un contrôleur de Session en périphérie (SBC), il est fortement recommandé que la configuration de jonction n’est pas associée à un enregistrement de l’utilisation de RTPC itinéraires vers une destination PSTN ou tous les autres systèmes en aval est connectés via Skype pour le serveur de l’entreprise. 
  
9. Organisez les enregistrements d’utilisation RTC pour obtenir des performances optimales. Pour modifier la position d’un enregistrement dans la liste, sélectionnez l’enregistrement de l’utilisation de TLS et cliquez sur la flèches ou bas.
    
    > [!IMPORTANT]
    > L’ordre des enregistrements d’utilisation RTC dans la liste de la configuration de jonction a son importance. Skype pour Business Server parcourt la liste de haut en bas. 
  
10. **Activer l’accrochage RTP** doit être sélectionné pour activer la déviation du trafic multimédia pour les clients se trouvant derrière un convertisseur d’adresses réseau (NAT) ou un pare-feu et un contrôleur SBC prenant en charge l’accrochage.
    
11. **Activer l’historique des appels de transfert** doit être sélectionné pour permettre l’envoi d’informations de l’historique des appels à l’homologue de la passerelle du serveur de médiation.
    
12. **Activer identité affirmée P transfèrent les données** doit être sélectionnée pour activer des informations d’expéditeur appel PAI devant être transmises entre le serveur de médiation et le côté de la passerelle (et inversement), lorsque la présente.
    
13. L’option **Activer le minuteur de basculement de routage de trafic sortant** doit être sélectionnée pour permettre un basculement rapide. La passerelle associée à cette jonction peut avertir dans les 10 secondes du traitement de l’appel sortant. Réacheminement vers un autre trunk se produira si cette notification n’est pas reçue par le serveur de médiation. Sur les réseaux dont la latence peut retarder le temps de réponse ou si la passerelle met plus de 10 secondes à répondre, le basculement rapide doit être désactivé.
    
14. (Facultatif) Associez et configurez les **règles de conversion du numéro d’appel** pour la jonction. Ces règles de conversion s’appliquent au numéro appelant pour les appels sortants
    
   - Pour choisir une ou plusieurs règles à partir d’une liste de toutes les règles de traduction qui sont disponibles dans votre déploiement de Voix Entreprise, cliquez sur **Sélectionner**. Dans **Sélectionner les règles de conversion**, cliquez sur les règles à associer à la jonction, puis cliquez sur **OK**.
    
   - Pour définir une nouvelle règle de conversion et l’associer à la jonction, cliquez sur **Nouvelle**. Pour plus d’informations sur les règles de traduction, consultez [règles de traduction dans Skype pour Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md).
    
   - Pour modifier une règle de conversion déjà associée à la jonction, cliquez sur le nom de la règle, puis sur **Afficher les détails**. 
    
   - Pour copier une règle de conversion existante à utiliser comme point de départ pour définir une nouvelle règle, sélectionnez le nom de la règle et cliquez sur **Copier**, puis sur **Coller**. 
    
   - Pour supprimer une règle de conversion de la jonction, sélectionnez le nom de la règle et cliquez sur **Supprimer**.
    
     > [!CAUTION]
     > N’associez pas de règles de conversion à une configuration de jonction si vous avez configuré les règles de conversion sur l’homologue de jonction associé, car les deux règles risquent d’entrer en conflit. 
  
15. (Facultatif) Associez et configurez les **règles de conversion de numéro appelé** pour la jonction. Les règles de conversion s’appliquent au numéro appelé dans un appel sortant.
    
   - Pour choisir une ou plusieurs règles à partir d’une liste de toutes les règles de traduction qui sont disponibles dans votre déploiement de Voix Entreprise, cliquez sur **Sélectionner**. Dans **Sélectionner les règles de conversion**, cliquez sur les règles à associer à la jonction, puis cliquez sur **OK**.
    
  - Pour définir une nouvelle règle de conversion et l’associer à la jonction, cliquez sur **Nouvelle**. Pour plus d’informations sur les règles de traduction, consultez [règles de traduction dans Skype pour Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/translation-rules.md).
    
   - Pour modifier une règle de conversion déjà associée à la jonction, cliquez sur le nom de la règle, puis sur **Afficher les détails**. 
    
   - Pour copier une règle de conversion existante à utiliser comme point de départ pour définir une nouvelle règle, sélectionnez le nom de la règle et cliquez sur **Copier**, puis sur **Coller**. 
    
   - Pour supprimer une règle de conversion de la jonction, sélectionnez le nom de la règle et cliquez sur **Supprimer**.
    
     > [!CAUTION]
     > N’associez pas de règles de conversion à une configuration de jonction si vous avez configuré les règles de conversion sur l’homologue de jonction associé, car les deux règles risquent d’entrer en conflit. 
  
16. Assurez-vous que les règles de traduction du tronc sont disposés dans l’ordre correct. Pour modifier la position d’une règle dans la liste, mettez en surbrillance le nom de la règle, puis cliquez sur haut ou flèche vers le bas.
    
    > [!IMPORTANT]
    > Skype pour Business Server parcourt la liste des règles de traduction à partir du haut vers le bas et utilise la première règle qui correspond le numéro composé. Si vous configurez une jonction de sorte qu’un numéro composé corresponde à plusieurs règles de conversion, vérifiez que les règles les plus restrictives s’affichent avant les règles les moins restrictives. Par exemple, si vous avez inclus une règle de traduction qui correspond à n’importe quel numéro à 11 chiffres et une règle de traduction qui correspond à seulement 11 chiffres qui commencent par +1425, assurez-vous que la règle qui correspond à n’importe quel numéro à 11 chiffres est triée *ci-dessous* la plus restrictive règle.
  
17. Lorsque vous avez fini de configurer la jonction, cliquez sur **OK**.
    
18. Dans la page **Configuration de la jonction**, cliquez sur **Valider**, puis sur **Tout valider**. 
    
    > [!NOTE]
    > Chaque fois que vous créez ou modifiez une configuration de jonction, vous devez exécuter la commande **Tout valider** pour publier la modification de la configuration. Pour plus d’informations, consultez [publication des modifications en attente à la configuration de routage voix dans Skype pour entreprise 2015](voice-route-config-changes.md) dans la documentation d’opérations.
  
## <a name="see-also"></a>Voir aussi

#### 

[Configurer une jonction avec le contournement de média dans Skype pour Business Server 2015](configure-trunk-with-media-bypass.md)
#### 

[Définition des règles de traduction](http://technet.microsoft.com/library/4f6b975a-77e6-474c-9171-b139d84138c2.aspx)

