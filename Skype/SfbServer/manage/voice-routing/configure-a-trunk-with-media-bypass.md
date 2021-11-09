---
title: 'Skype Entreprise Server : configurer une trunk avec la déviation du média'
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Comment configurer une trunk avec la déviation du média activée. "
ms.openlocfilehash: 3255aa946cdbec46bf76860d64fe2ca367862a50
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60861251"
---
# <a name="skype-for-business-server---configure-a-trunk-with-media-bypass"></a>Skype Entreprise Server : configurer une trunk avec la déviation du média 

Suivez ces étapes pour configurer une trunk avec la déviation du média activée. Pour configurer une trunk avec la déviation du média désactivée, voir Configurer une trunk sans déviation du média [dans Skype Entreprise Server](configure-a-trunk-without-media-bypass.md). Le contournement de média est utile lorsque vous voulez réduire le nombre de serveurs de médiation déployés. Un pool de serveurs de médiation est généralement déployé sur un site central et contrôle des passerelles sur des sites de succursale. L’activation du contournement de média permet aux médias de passer des appels PSTN (Public Switched Telephone Network) depuis des clients situés sur les sites de succursale directement par les passerelles de ces sites. Skype Entreprise Server les itinéraires d’appels sortants et les stratégies de Voix Entreprise doivent être correctement configurés afin que les appels PSTN des clients d’un site de succursale soient acheminés vers la passerelle appropriée.

Nous vous recommandons vivement d’activer le contournement de média. Toutefois, avant d’activer le contournement de média sur une trunk SIP, confirmez que votre fournisseur de trunks SIP qualifié prend en charge le contournement de média et est en mesure de répondre aux exigences permettant d’activer correctement le scénario. Plus précisément, le fournisseur doit avoir les adresses IP des serveurs du réseau interne de votre organisation. Si le fournisseur ne peut pas la prise en charge de ce scénario, le contournement de média ne réussira pas. Pour plus d’informations, [voir Plan for media bypass in Skype Entreprise](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md).

> [!NOTE]
> La déviation du trafic multimédia ne fonctionne pas avec toutes les passerelles de réseau téléphonique commuté (PSTN), IP-PBX et contrôleur de frontière de session (SBC). Microsoft a testé un ensemble de passerelles PSTN et de SCS avec des partenaires certifiés et a effectué des tests avec cisco IP-PBX. La déviation du trafic multimédia est prise en charge uniquement avec les produits et les versions répertoriés sur la page Infrastructure téléphonique [Skype Entreprise Server](../../../SfbPartnerCertification/certification/infra-gateways.md) web. 


Une configuration de la trunk comme décrit ci-dessous groupe un ensemble de paramètres qui sont appliqués aux trunks affectés à cette configuration de trunk. Une configuration de jonction spécifique peut s’étendre au niveau global (à toutes les jonctions qui ne disposent plus d’une configuration de site ou de pool spécifique) ou au niveau d’un site ou d’un pool. La configuration de jonction au niveau du pool est utilisée pour étendre une configuration de jonction spécifique à une jonction unique.

**Pour configurer une trunk avec la déviation du média**

1. Ouvrez Skype panneau de commande Busines Server.
2. Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Configuration de la jonction**.
3. Dans la page **Configuration de la jonction**, configurez une jonction à l’aide de l’une des méthodes suivantes :
    - Double-cliquez sur une jonction existante (par exemple, la jonction **Global**) pour afficher la boîte de dialogue **Modifier la configuration de la jonction**.
    - Cliquez sur **Nouvelle**, puis sélectionnez l’étendue de la nouvelle configuration de jonction :
        - **Site trunk:** Choose the site for this trunk configuration from **Select a Site,** and then click **OK**. Notez que si une configuration de trunk a déjà été créée pour un site, le site n’apparaît pas dans **Sélectionner un site.** Cette configuration de la trunk sera appliquée à toutes les trunks du site.
        - **Pool trunk:** Choose the name of the trunk that this trunk configuration applies to. Cette trunk peut être la racine ou toute autre trunks supplémentaire définie dans le Générateur de topologie. Dans **Sélectionner un service,** cliquez sur **OK.** Notez que si une configuration de trunk a déjà été créée pour une trunk spécifique, la trunk n’apparaît pas dans **Select a Service**.
    
    > [!NOTE]
    > Une fois que vous avez sélectionné l’étendue de la configuration de jonction, elle n’est plus modifiable. Le champ **Nom** est prérempli et comporte le nom du site ou service associé à la configuration de jonction. Ce nom n’est pas modifiable. 

5. Spécifiez une valeur dans **le nombre maximal de boîtes de dialogue anticipées pris en charge.** Il s’agit du nombre maximal de réponses bifurcations qu’une passerelle PSTN, un système IP-PBX ou un contrôleur SBC (Session Border Controller) itsp peut recevoir à une invitation qu’il a envoyée au serveur de médiation. La valeur par défaut est 20.

    > [!NOTE] 
    > Avant de modifier cette valeur, consultez votre fournisseur de services ou votre fabricant d’équipements pour plus d’informations sur les fonctionnalités de votre système. 

6. Sélectionnez l’une des options de **Niveau de prise en charge du chiffrement** :
    - **Requis** : le chiffrement SRTP (Secure Real-time Transport Protocol) doit être utilisé pour aider à protéger le trafic entre le serveur de médiation et la passerelle ou le système PBX (private branch exchange).
    - **Facultatif** : le chiffrement SRTP sera utilisé s’il est pris en charge par le fournisseur de services ou le fabricant.
    - **Non pris en charge** : le chiffrement SRTP n’étant pas pris en charge pas le fournisseur de services ou le fabricant, il ne peut pas être utilisé.
7. Activez la **case à** cocher Activer le contournement de média si vous souhaitez que le média contourne le serveur de médiation pour le traitement par l’homologue de la trunk.

    > [!IMPORTANT]
    > Pour que la déviation du trafic multimédia fonctionne correctement, la passerelle PSTN, le système IP-PBX ou le contrôleur de frontière de session ITSP doit prendre en charge certaines fonctionnalités. Pour plus d’informations, [voir Plan for media bypass in Skype Entreprise](../../plan-your-deployment/enterprise-voice-solution/media-bypass.md). 

8. Cochez la case Traitement multimédia centralisé s’il existe un point de terminaison multimédia connu (par exemple, une passerelle PSTN où la terminaison multimédia a la même adresse IP que la terminaison de signalisation).  Désactivez cette case à cocher si la jonction ne comporte pas de point de terminaison multimédia connu.
9. Si l’homologue de la passerelle prend en charge la réception de demandes SIP REFER à partir du serveur de médiation, activez la case à cocher Activer l’envoi pour **la** passerelle. 

    > [!NOTE] 
    > Si vous désactivez cette option lorsque l’option Activer le contournement **de** média est sélectionnée, des paramètres supplémentaires sont requis. Si l’homologue de la connexion ne prend pas en charge la réception de demandes SIP REFER du serveur de médiation et que le contournement de média est activé, vous devez également exécuter l’cmdlet **Set-CsTrunkConfiguration** pour désactiver le protocole RTCP pour les appels actifs et en cours afin de prendre en charge les conditions adéquates pour le contournement de média. Vous pouvez également  sélectionner Activer la référence à l’aide d’un contrôle d’appel tiers si vous souhaitez que les appels transférés soient contourné par le média, et que la passerelle ne prend pas en charge les demandes SIP REFER. 

10. (Facultatif) Pour permettre le routage interjonction, associez et configurez les enregistrements d’utilisation PSTN à la configuration de cette jonction. Les utilisations PSTN associées à cette configuration de Skype Entreprise Server sont appliquées pour tous les appels entrants via la Skype Entreprise Server point de terminaison. Pour gérer les enregistrements d’utilisation PSTN associés à une configuration de jonction, utilisez l’une des méthodes suivantes :
    - Pour sélectionner un ou plusieurs enregistrements dans une liste de tous les enregistrements d’utilisation PSTN disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner.** Sélectionnez les enregistrements à associer à cette configuration de jonction, puis cliquez sur **OK**.
    - Pour supprimer un enregistrement d’utilisation PSTN de cette configuration de jonction, sélectionnez l’enregistrement, puis cliquez sur **Supprimer**.
    - Pour définir un nouvel enregistrement d’utilisation PSTN et l’associer à cette configuration de jonction, procédez comme suit :
        1. Cliquez sur **Nouveau**.
        2. Dans le champ **Nom**, indiquez un nom descriptif unique pour l’enregistrement.
            > [!NOTE] 
            > Le nom de l’enregistrement d’utilisation PSTN doit être unique dans le déploiement Voix Entreprise. Une fois que l’enregistrement est enregistré, le champ **Nom** ne peut plus être modifié. 
        3. Utilisez l’une des méthodes suivantes pour associer et configurer les itinéraires pour cet enregistrement d’utilisation PSTN :
            - Pour sélectionner un ou plusieurs itinéraires dans la liste de tous les itinéraires disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner.** Sélectionnez les itinéraires que vous voulez associer à cet enregistrement d’utilisation PSTN, puis cliquez sur **OK**. 
            - Pour supprimer un itinéraire de l’enregistrement d’utilisation PSTN, sélectionnez l’itinéraire et cliquez sur **Supprimer**.
            - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation PSTN, cliquez sur **Nouveau**. 
            - Pour modifier un itinéraire associé à cet enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**. 
        4. Cliquez sur **OK**.
    - Pour modifier un enregistrement d’utilisation PSTN déjà associé à cette configuration de jonction, procédez comme suit :
        1. Sélectionnez l’enregistrement d’utilisation PSTN que vous voulez modifier, puis cliquez sur **Afficher les détails**.
        2. Utilisez l’une des méthodes suivantes pour associer et configurer les itinéraires pour cet enregistrement d’utilisation PSTN :
            - Pour sélectionner un ou plusieurs itinéraires dans la liste de tous les itinéraires disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner.** Sélectionnez les itinéraires que vous voulez associer à cet enregistrement d’utilisation PSTN, puis cliquez sur **OK**. 
            - Pour supprimer un itinéraire de l’enregistrement d’utilisation PSTN, sélectionnez l’itinéraire et cliquez sur **Supprimer**.
            - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation PSTN, cliquez sur **Nouveau**. 
            - Pour modifier un itinéraire associé à cet enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**. 
        3. Cliquez sur **OK**.

    > [!Important]
    > Il est important d’associer des enregistrements d’utilisation PSTN en fonction de l’homologue du serveur de médiation associé à la trunk en cours de configuration. Si l’homologue du serveur de médiation est une passerelle PSTN ou un contrôleur de frontière de session (SBC), il est vivement recommandé que la configuration de la connexion ne soit pas associée à un enregistrement d’utilisation PSTN qui approvisionnement vers une destination PSTN ou tout autre système en aval connecté via Skype Entreprise Server. 

11. Organisez les enregistrements d’utilisation PSTN pour obtenir des performances optimales. Pour changer la position d’un enregistrement dans la liste, sélectionnez l’enregistrement d’utilisation PSTN, puis cliquez sur la flèche vers le haut ou vers le bas.

    > [!Important]
    > L’ordre des enregistrements d’utilisation PSTN dans la liste de la configuration de jonction a son importance. Skype Entreprise Server la liste de haut en bas. 

12. **L’activer** doit être sélectionné pour activer le contournement de média pour les clients derrière une traduction d’adresses réseau (NAT) ou un pare-feu et un SBC qui prend en charge l’verrou.
13. **Activez l’historique des** appels de transmission pour permettre l’envoi d’informations d’historique des appels à l’homologue de passerelle du serveur de médiation.
14. Activez le forward **P-Asserted-Identity** pour activer les informations d’origine de l’appel PAI (P-Asserted-Identity) entre le côté serveur de médiation et le côté passerelle (et vice versa), le cas présent.
15. **Activer le minuteur de basculement de routage de trafic sortant** doit être sélectionné pour permettre un basculement rapide. La passerelle associée à cette jonction peut informer dans les 10 secondes du traitement de l’appel sortant. Le réroutage vers une autre ligne se produit si cette notification n’est pas reçue par le serveur de médiation. Sur des réseaux avec une latence qui peut retarder le temps de réponse ou si la passerelle prend plus de 10 secondes à répondre, le basculement rapide doit être désactivé.
16. (Facultatif) Associez et configurez les **règles de traduction du numéro d’appel** pour la jonction. Ces règles de traduction s’appliquent au numéro appelant pour les appels sortants.
    - Pour choisir une ou plusieurs règles dans une liste de toutes les règles de traduction disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner.** Dans **Sélectionner les règles de traduction**, cliquez sur les règles à associer à la jonction, puis cliquez sur **OK**.
    - Si vous voulez définir une nouvelle règle de traduction et l’associer à la jonction, cliquez sur **Nouvelle**. Pour plus d’informations sur la définition d’une nouvelle règle, voir [Defining translation rules in Skype Entreprise Server](defining-translation-rules.md).
    - Pour modifier une règle de traduction associée à une jonction, cliquez sur son nom, puis sur **Afficher les détails**. Pour plus d’informations, [voir Defining translation rules in Skype Entreprise Server](defining-translation-rules.md).
    - Pour copier une règle de traduction existante qui servira de point de départ à la définition d’une nouvelle règle, cliquez sur son nom, sur **Copier**, puis sur **Coller**. Pour plus d’informations, [voir Defining translation rules in Skype Entreprise Server](defining-translation-rules.md).
    - Pour supprimer une règle de traduction d’une jonction, sélectionnez son nom, puis cliquez sur **Supprimer**.
    > [!Warning]
    > N’associez pas de règles de traduction à une configuration de jonction si vous avez configuré les règles de traduction sur l’homologue de jonction associé, car les deux règles risqueraient d’entrer en conflit. 

17. (Facultatif) Associez et configurez les **règles de traduction de numéro appelé** pour la jonction. Les règles de traduction s’appliquent au numéro appelé dans un appel sortant.
    - Pour choisir une ou plusieurs règles dans une liste de toutes les règles de traduction disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner.** Dans **Sélectionner les règles de traduction**, cliquez sur les règles à associer à la jonction, puis cliquez sur **OK**.
    - Si vous voulez définir une nouvelle règle de traduction et l’associer à la jonction, cliquez sur **Nouvelle**. Pour plus d’informations sur la définition d’une nouvelle règle, voir [Defining translation rules in Skype Entreprise Server](defining-translation-rules.md).
    - Pour modifier une règle de traduction associée à une jonction, cliquez sur son nom, puis sur **Afficher les détails**. Pour plus d’informations, [voir Defining translation rules in Skype Entreprise Server](defining-translation-rules.md).
    - Pour copier une règle de traduction existante qui servira de point de départ à la définition d’une nouvelle règle, cliquez sur son nom, sur **Copier**, puis sur **Coller**. Pour plus d’informations, [voir Defining translation rules in Skype Entreprise Server](defining-translation-rules.md).
    - Pour supprimer une règle de traduction d’une jonction, sélectionnez son nom, puis cliquez sur **Supprimer**.

    > [!Warning] 
    > N’associez pas de règles de traduction à une configuration de jonction si vous avez configuré les règles de traduction sur l’homologue de jonction associé, car les deux règles risqueraient d’entrer en conflit. 

18. Assurez-vous que les règles de traduction de la trunk sont organisées dans l’ordre correct. Pour déplacer une règle dans la liste, sélectionnez-la, puis cliquez sur la flèche vers le haut ou vers le bas.

    >[!Important] 
    > Skype Entreprise Server parcourt la liste des règles de traduction de haut en bas et utilise la première règle qui correspond au numéro composé. Si vous configurez une jonction de sorte qu’un numéro composé corresponde à plusieurs règles de traduction, assurez-vous que les règles les plus restrictives apparaissent avant les règles les moins restrictives. Par exemple, si une règle de traduction s’applique à tout numéro à 11 chiffres et une autre s’applique à tout numéro à 11 chiffres commençant par +1425, assurez-vous que la règle qui s’applique à tout numéro à 11 chiffres apparaît *après* la règle la plus restrictive. 

19. Lorsque vous avez terminé de configurer la jonction, cliquez sur **OK**.
20. Dans la page **Configuration de la jonction**, cliquez sur **Valider**, puis sur **Valider tout**. 

    > [!Note]
    > À chaque fois que vous créez ou modifiez une configuration de jonction, vous devez exécuter la commande **Valider tout** pour publier la modification de la configuration. Pour plus d’informations, voir [Publier les modifications en attente de la configuration du routage des voix.](/previous-versions/office/lync-server-2013/lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration) (VOUS AVEZ BESOIN D’UN NOUVEAU LIEN ?)

Une fois que vous avez configuré la trunk, continuez à configurer le contournement de média en choisissant entre les options de déviation du média globale, comme décrit dans [Deploy media bypass in Skype Entreprise Server](../../deploy/deploy-enterprise-voice/deploy-media-bypass.md).
