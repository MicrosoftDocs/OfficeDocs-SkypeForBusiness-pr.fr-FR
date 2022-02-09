---
title: 'Skype Entreprise Server : configurer une trunk sans contournement de média'
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 'Comment configurer une trunk avec la déviation du média activée. '
ms.openlocfilehash: 5b6342b558de40d04771104cf4a8bd011aaea363
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62401888"
---
# <a name="skype-for-business-server---configure-a-trunk-without-media-bypass"></a>Skype Entreprise Server : configurer une trunk sans contournement de média

Pour configurer une jonction sur laquelle le contournement de média est désactivé, procédez comme suit. Si vous souhaitez configurer une trunk avec la déviation du média activée, voir Configurer une trunk avec la déviation du média [dans Skype Entreprise Server](configure-a-trunk-with-media-bypass.md).

Une configuration de jonction, comme décrit plus bas, regroupe un ensemble de paramètres appliqués aux jonctions affectées à cette configuration de jonction. Une configuration de jonction spécifique peut s’étendre au niveau global (à toutes les jonctions qui ne disposent plus d’une configuration de site ou de pool spécifique) ou au niveau d’un site ou d’un pool. La configuration de jonction au niveau du pool est utilisée pour étendre une configuration de jonction spécifique à une jonction unique.

**Pour configurer une jonction sans contournement de média**

1. Ouvrez Skype panneau de commande Busines Server.
3. Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Configuration de la jonction**.
4. Dans la page **Configuration de la jonction**, configurez une jonction à l’aide de l’une des méthodes suivantes :
    - Double-cliquez sur une jonction existante (par exemple, la jonction **Global**) pour afficher la boîte de dialogue **Modifier la configuration de la jonction**.
    - Cliquez sur **Nouvelle**, puis sélectionnez l’étendue de la nouvelle configuration de jonction :
        - **Site trunk**: Choose the site for this trunk configuration in **Select a Site**, and then click **OK**. Notez que si une configuration de trunk a déjà été créée pour un site, le site n’apparaît pas dans **Sélectionner un site**. Cette configuration de la trunk sera appliquée à toutes les trunks du site.
        - **Pool trunk**: Choose the name of the trunk that this trunk configuration applies to in **Select a Service** and click **OK**. Cette trunk peut être la racine ou toute autre trunks supplémentaire définie dans le Générateur de topologie. Notez que si une configuration de trunk a déjà été créée pour une trunk spécifique, la trunk n’apparaît pas dans **Select a Service**.
    > [!Note] 
    > Une fois que vous avez sélectionné l’étendue de la configuration de jonction, elle n’est plus modifiable. Le champ **Nom** est prérempli et comporte le nom du site ou service associé à la configuration de jonction. Ce nom n’est pas modifiable. 

5. Sélectionnez l’une des options de **Niveau de prise en charge du chiffrement** :
    - **Requis** : le chiffrement SRTP (Secure Real-time Transport Protocol) doit être utilisé pour aider à protéger le trafic entre le serveur de médiation et la passerelle ou le système PBX (private branch exchange).
    - **Facultatif** : le chiffrement SRTP sera utilisé s’il est pris en charge par le fournisseur de services ou le fabricant.
    - **Non pris en charge** : le chiffrement SRTP n’étant pas pris en charge pas le fournisseur de services ou le fabricant, il ne peut pas être utilisé.
6. Assurez-vous que la case à cocher **Activer le contournement de média** est désactivée.
7. Activez la case à cocher **Traitement multimédia centralisé** si un point de terminaison média connu existe (par exemple, une passerelle PSTN sur laquelle la terminaison multimédia possède la même adresse IP que la terminaison de signalisation). Désactivez cette case à cocher si la jonction ne comporte pas de point de terminaison multimédia connu.
8. Si l’homologue de la passerelle prend en charge la réception de demandes SIP REFER à partir du serveur de médiation, activez la case à cocher Activer l’envoi pour **la** passerelle.
9. (Facultatif) Pour permettre le routage interjonction, associez et configurez les enregistrements d’utilisation PSTN à la configuration de cette jonction. Les utilisations PSTN associées à cette configuration de Skype Entreprise Server sont appliquées pour tous les appels entrants via la Skype Entreprise Server point de terminaison. Pour gérer les enregistrements d’utilisation PSTN associés à une configuration de jonction, utilisez l’une des méthodes suivantes :
    - Pour sélectionner un ou plusieurs enregistrements dans une liste de tous les enregistrements d’utilisation PSTN disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner**. Sélectionnez les enregistrements à associer à cette configuration de jonction, puis cliquez sur **OK**.
    - Pour supprimer un enregistrement d’utilisation PSTN de cette configuration de jonction, sélectionnez l’enregistrement, puis cliquez sur **Supprimer**.
    - Pour définir un nouvel enregistrement d’utilisation PSTN et l’associer à cette configuration de jonction, procédez comme suit :
        1. Cliquez sur **Nouveau**.
        2. Dans le champ **Nom**, indiquez un nom descriptif unique pour l’enregistrement.
            > [!Note] 
            > Le nom de l’enregistrement d’utilisation PSTN doit être unique dans le déploiement Voix Entreprise. Une fois que l’enregistrement est enregistré, le champ **Nom** ne peut plus être modifié. 

        3. Utilisez l’une des méthodes suivantes pour associer et configurer les itinéraires pour cet enregistrement d’utilisation PSTN :
            - Pour sélectionner un ou plusieurs itinéraires dans la liste de tous les itinéraires disponibles dans Voix Entreprise déploiement, cliquez sur **Sélectionner**. Sélectionnez les itinéraires que vous voulez associer à cet enregistrement d’utilisation PSTN, puis cliquez sur **OK**. 
            - Pour supprimer un itinéraire de l’enregistrement d’utilisation PSTN, sélectionnez l’itinéraire et cliquez sur **Supprimer**.
            - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation PSTN, cliquez sur **Nouveau**. 
            - Pour modifier un itinéraire associé à cet enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**. 
        4. Cliquez sur **OK**.
    - Pour modifier un enregistrement d’utilisation PSTN déjà associé à cette configuration de jonction, procédez comme suit :
        1. Sélectionnez l’enregistrement d’utilisation PSTN que vous voulez modifier, puis cliquez sur **Afficher les détails**.
        2. Utilisez l’une des méthodes suivantes pour associer et configurer les itinéraires pour cet enregistrement d’utilisation PSTN :
            - Pour sélectionner un ou plusieurs itinéraires dans la liste de tous les itinéraires disponibles dans Voix Entreprise déploiement, cliquez sur **Sélectionner**. Sélectionnez les itinéraires que vous voulez associer à cet enregistrement d’utilisation PSTN, puis cliquez sur **OK**. 
            - Pour supprimer un itinéraire de l’enregistrement d’utilisation PSTN, sélectionnez l’itinéraire et cliquez sur **Supprimer**.
            - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation PSTN, cliquez sur **Nouveau**. 
            - Pour modifier un itinéraire associé à cet enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**. 
        3. Cliquez sur **OK**.

    > [!Important] 
    > Il est important d’associer les enregistrements d’utilisation PSTN en fonction de l’homologue du serveur de médiation associé à la trunk en cours de configuration. Si l’homologue du serveur de médiation est une passerelle PSTN ou un contrôleur de frontière de session (SBC), il est vivement recommandé que la configuration de la connexion ne soit pas associée à un enregistrement d’utilisation PSTN qui approvisionnement vers une destination PSTN ou tout autre système en aval connecté via Skype Entreprise Server. 

10. Organisez les enregistrements d’utilisation PSTN pour obtenir des performances optimales. Pour changer la position d’un enregistrement dans la liste, sélectionnez l’enregistrement d’utilisation PSTN, puis cliquez sur la flèche vers le haut ou vers le bas.
    > [!Important] 
    > L’ordre des enregistrements d’utilisation PSTN dans la liste de la configuration de jonction a son importance. Skype Entreprise Server la liste de haut en bas. 

11. **Activer l’accrochage RTP** doit être sélectionné pour activer la déviation du trafic multimédia pour les clients se trouvant derrière une NAT ou un pare-feu et un contrôleur SBC prenant en charge l’accrochage.
12. **L’activer doit** être sélectionné pour activer l’envoi d’informations d’historique des appels à l’homologue de passerelle du serveur de médiation.
13. **Activez le forward P-Asserted-Identity** pour que les informations d’origine de l’appel PAI soient transmis entre le serveur de médiation et le côté passerelle (et vice versa), le cas présent.
14. **Activer le minuteur de basculement de routage de trafic sortant** doit être sélectionné pour permettre un basculement rapide. La passerelle associée à cette jonction peut informer dans les 10 secondes du traitement de l’appel sortant. Le réroutage vers une autre ligne se produit si cette notification n’est pas reçue par le serveur de médiation. Sur des réseaux avec une latence qui peut retarder le temps de réponse ou si la passerelle prend plus de 10 secondes à répondre, le basculement rapide doit être désactivé.
15. (Facultatif) Associez et **configurez des règles de traduction de numéro d’appel** pour la trunk. Ces règles de traduction s’appliquent au numéro appelant pour les appels sortants.
    - Pour choisir une ou plusieurs règles dans une liste de toutes les règles de traduction disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner**. Dans **Sélectionner les règles de traduction**, cliquez sur les règles à associer à la jonction, puis cliquez sur **OK**.
    - Si vous voulez définir une nouvelle règle de traduction et l’associer à la jonction, cliquez sur **Nouvelle**. Pour plus d’informations sur la définition d’une nouvelle règle, voir [Defining translation rules in Skype Entreprise Server](defining-translation-rules.md).
    - Pour modifier une règle de traduction associée à une jonction, cliquez sur son nom, puis sur **Afficher les détails**. Pour plus d’informations, [voir Defining translation rules in Skype Entreprise Server](defining-translation-rules.md).
    - Pour copier une règle de traduction existante qui servira de point de départ à la définition d’une nouvelle règle, cliquez sur son nom, sur **Copier**, puis sur **Coller**. Pour plus d’informations, [voir Defining translation rules in Skype Entreprise Server](defining-translation-rules.md).
    - Pour supprimer une règle de traduction d’une jonction, sélectionnez son nom, puis cliquez sur **Supprimer**.

    > [!Warning]
    > N’associez pas de règles de traduction à une configuration de jonction si vous avez configuré les règles de traduction sur l’homologue de jonction associé, car les deux règles risqueraient d’entrer en conflit. 

16. (Facultatif) Associez et configurez les **règles de traduction de numéro appelé** pour la jonction. Les règles de traduction s’appliquent au numéro appelé dans un appel sortant.
    - Pour choisir une ou plusieurs règles dans une liste de toutes les règles de traduction disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner**. Dans Sélectionner les règles de traduction, cliquez sur les règles que vous souhaitez associer à la trunk, puis cliquez sur **OK**.
    - Si vous voulez définir une nouvelle règle de traduction et l’associer à la jonction, cliquez sur **Nouvelle**. Pour plus d’informations sur la définition d’une nouvelle règle, voir [Defining translation rules in Skype Entreprise Server](defining-translation-rules.md).
    - Pour modifier une règle de traduction associée à une jonction, cliquez sur son nom, puis sur **Afficher les détails**. Pour plus d’informations, [voir Defining translation rules in Skype Entreprise Server](defining-translation-rules.md).
    - Pour copier une règle de traduction existante qui servira de point de départ à la définition d’une nouvelle règle, cliquez sur son nom, sur **Copier**, puis sur **Coller**. Pour plus d’informations, [voir Defining translation rules in Skype Entreprise Server](defining-translation-rules.md).
    - Pour supprimer une règle de traduction d’une jonction, sélectionnez son nom, puis cliquez sur **Supprimer**.

    > [!Caution] 
    > N’associez pas de règles de traduction à une configuration de jonction si vous avez configuré les règles de traduction sur l’homologue de jonction associé, car les deux règles risqueraient d’entrer en conflit. 

17. Assurez-vous que les règles de traduction de la trunk sont organisées dans l’ordre correct. Pour déplacer une règle dans la liste, sélectionnez-la, puis cliquez sur la flèche vers le haut ou vers le bas.

    > [!Important] 
    > Skype Entreprise Server parcourt la liste des règles de traduction de haut en bas et utilise la première règle qui correspond au numéro composé. Si vous configurez une jonction de sorte qu’un numéro composé corresponde à plusieurs règles de traduction, assurez-vous que les règles les plus restrictives apparaissent avant les règles les moins restrictives. Par exemple, si une règle de traduction s’applique à tout numéro à 11 chiffres et une autre s’applique à tout numéro à 11 chiffres commençant par +1425, assurez-vous que la règle qui s’applique à tout numéro à 11 chiffres apparaît après la règle la plus restrictive. 

18. Lorsque vous avez terminé de configurer la jonction, cliquez sur **OK**.
19. Dans la page **Configuration de la jonction**, cliquez sur **Valider**, puis sur **Valider tout**. 

    > [!Note]
    > À chaque fois que vous créez ou modifiez une configuration de jonction, vous devez exécuter la commande **Valider tout** pour publier la modification de la configuration. Pour plus d’informations, voir Publish pending changes to the voice routing configuration in Lync Server 2013 in the Operations documentation. 
