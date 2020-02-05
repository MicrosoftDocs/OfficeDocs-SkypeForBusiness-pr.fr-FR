---
title: Déploiement de serveurs Edge dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 63c7251c-080a-4175-99a6-f86d0266d6bc
description: 'Résumé : Découvrez comment déployer des serveurs Edge dans votre environnement Skype entreprise Server.'
ms.openlocfilehash: 5411c2934191aba1f4efb8eabf5e909c8cad710e
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768307"
---
# <a name="deploy-edge-servers-in-skype-for-business-server"></a>Déploiement de serveurs Edge dans Skype entreprise Server
 
**Résumé :** Découvrez comment déployer des serveurs Edge dans votre environnement Skype entreprise Server.
  
Les sections suivantes décrivent les étapes devant être suivies après le déploiement de Skype entreprise Server [pour les déploiements de serveur Edge dans la documentation de Skype entreprise Server](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) . Les étapes de déploiement sont les suivantes :
  
- Interfaces réseau
    
- Installation
    
- Certificats
    
- Démarrage des serveurs de périphérie
    
## <a name="network-interfaces"></a>Interfaces réseau

Comme indiqué dans la rubrique planification, vous allez configurer votre interface réseau avec DNS dans le réseau de périmètre qui héberge vos serveurs de périphérie ou sans DNS dans le réseau de périmètre.
  
### <a name="interface-configuration-with-dns-servers-in-the-perimeter-network"></a>Configuration des interfaces avec des serveurs DNS dans le réseau de périmètre

1. Installez deux cartes réseau pour chaque serveur Edge, une pour l’interface interne et une pour l’interface externe.
    
    > [!NOTE]
    > Les sous-réseaux interne et externe ne doivent pas être routables entre eux. 
  
2. Sur votre interface externe, vous configurez l' **une** des options suivantes :
    
   a. Trois adresses IP statiques sur le sous-réseau de périmètre externe et pointez la passerelle par défaut vers l’interface interne du pare-feu externe. Configurez les paramètres DNS de l’adaptateur de façon à ce qu’ils pointent vers une paire de serveurs DNS de périmètre.
    
   b. Une adresse IP statique sur le sous-réseau de périmètre externe et pointez la passerelle par défaut vers l’interface interne du pare-feu externe. Configurez les paramètres DNS de l’adaptateur de façon à ce qu’ils pointent vers une paire de serveurs DNS de périmètre. Cette configuration est acceptable uniquement si vous avez déjà configuré votre topologie pour disposer de valeurs non standard dans les affectations de port, qui est décrite dans l’article [créer votre topologie de périphérie pour Skype entreprise Server](create-your-edge-topology.md) .
    
3. Sur votre interface interne, configurez une adresse IP statique sur le sous-réseau de périmètre interne et ne définissez aucune passerelle par défaut. Configurez les paramètres de la carte réseau DNS de manière à pointer vers au moins un serveur DNS, de préférence une paire de serveurs DNS de périmètre.
    
4. Créez des itinéraires statiques persistants sur l’interface interne vers tous les réseaux internes dans lesquels résident les clients, Skype entreprise Server et les serveurs de messagerie unifiée Exchange.
    
### <a name="interface-configuration-without-dns-servers-in-the-perimeter-network"></a>Configuration des interfaces sans serveur DNS dans le réseau de périmètre

1. Installez deux cartes réseau pour chaque serveur Edge, une pour l’interface interne et une pour l’interface externe.
    
    > [!NOTE]
    > Les sous-réseaux interne et externe ne doivent pas être routables entre eux. 
  
2. Sur votre interface externe, vous configurez l' **une** des options suivantes :
    
   a. Trois adresses IP statiques du sous-réseau de périmètre externe. Vous devez également configurer la passerelle par défaut sur l’interface externe (par exemple, pour définir le routeur Internet ou le pare-feu externe comme passerelle par défaut). Configurez les paramètres DNS de l’adaptateur de manière à ce qu’ils pointent vers un serveur DNS externe, idéalement une paire de serveurs DNS externes.
    
   b. Une adresse IP statique sur le sous-réseau du réseau de périmètre extérieur. Vous devez également configurer la passerelle par défaut sur l’interface externe (par exemple, pour définir le routeur Internet ou le pare-feu externe comme passerelle par défaut). Configurez les paramètres de la carte réseau DNS de manière à pointer vers une paire de serveurs DNS externes. Cette configuration est acceptable uniquement si vous avez déjà configuré votre topologie pour disposer de valeurs non standard dans les affectations de port, qui est décrite dans l’article [créer votre topologie de périphérie pour Skype entreprise Server](create-your-edge-topology.md) .
    
3. Sur votre interface interne, configurez une adresse IP statique sur le sous-réseau de périmètre interne et ne définissez aucune passerelle par défaut. Laissez les paramètres DNS de la carte réseau vides.
    
4. Créez des itinéraires statiques persistants sur l’interface interne vers tous les réseaux internes dans lesquels résident les clients, Skype entreprise Server et les serveurs de messagerie unifiée Exchange.
    
5. Modifiez le fichier hôte sur chaque serveur Edge pour qu’il contienne un enregistrement pour le serveur du tronçon suivant ou l’adresse IP virtuelle. Cet enregistrement sera le directeur, le serveur Standard Edition Server ou le pool frontal que vous avez configuré comme serveur Edge à partir de l’adresse tronçon suivant dans le générateur de topologie. Si vous utilisez l’équilibrage de charge DNS, incluez une ligne pour chaque membre du pool de prochains tronçons.
    
## <a name="installation"></a>Installation

Pour effectuer ces étapes, vous devez suivre les étapes décrites dans l’article [créer votre topologie Edge pour Skype entreprise Server](create-your-edge-topology.md) .
  
1. Ouvrez une session sur le serveur que vous avez configuré pour le rôle serveur Edge avec un compte qui se trouve dans le groupe de l’administrateur local.
    
2. Vous aurez besoin du fichier de configuration topologique que vous avez copié à la fin de la documentation relative à la topologie du serveur Edge sur cet ordinateur. Accédez au support externe (clé USB ou partage) sur lequel vous avez placé ce fichier de configuration.
    
3. Démarrez l' **Assistant Déploiement**.
    
4. Lorsque l’Assistant s’ouvre, cliquez sur **installer ou mettre à jour le système Skype entreprise Server**.
    
5. L’assistant exécute des tests pour voir si un élément est déjà installé. Comme c’est la première fois que vous exécutez l’Assistant, vous pouvez commencer à l' **étape 1. Installez le magasin de configuration local.**
    
6. La boîte **de dialogue Configurer le réplica local du magasin de gestion central** s’affiche. Vous devez cliquer sur **Importer à partir d’un fichier (recommandé pour les serveurs Edge)**.
    
7. De là, accédez à l’emplacement de la topologie exportée, sélectionnez le fichier .zip, cliquez sur **Ouvrir**, puis sur **Suivant**.
    
8. L’Assistant Déploiement va lire le fichier de configuration et écrire le fichier de configuration XML sur l’ordinateur local.
    
9. Une fois que la procédure **Exécution de commandes** est terminé, cliquez sur **Terminer**.
    
10. Dans l’Assistant Déploiement, cliquez sur **étape 2. Configurer ou supprimer des composants de Skype entreprise Server**. L’Assistant va alors installer les composants Edge de Skype entreprise Server spécifiés dans le fichier de configuration XML stocké sur l’ordinateur local.
    
11. Une fois l’installation terminée, vous pouvez passer aux étapes de la section **certificats** ci-dessous.
    
## <a name="certificates"></a>Certificats

Pour plus d’informations, consultez la documentation de planification des certificats de serveur Edge. Les étapes de configuration des certificats figurent ci-dessous.
  
> [!NOTE]
> Lors de l’exécution de l’Assistant certificat, vous devez être connecté en tant que compte disposant des autorisations appropriées pour le type de modèle de certificat que vous souhaitez utiliser. Par défaut, une demande de certificat de serveur Skype entreprise va utiliser le modèle de certificat de serveur Web. Si vous avez ouvert une session avec un compte membre du groupe RTCUniversalServerAdmins pour demander un certificat via ce modèle, vérifiez que le groupe a été doté de l’autorisation d’inscription pour utiliser ce modèle. 
  
### <a name="internal-edge-interface-certificates"></a>Certificats d’interface interne de serveur Edge

 
### <a name="1-download-or-export-the-ca-certification-chain"></a>1. Télécharger ou exporter la chaîne de certification de l’autorité de certification

 
#### <a name="nbspnbspnbsp-a-download-using-certsrv-web-site"></a>&nbsp;&nbsp;&nbsp;un. Télécharger à l’aide du site web certsrv

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ma. Connectez-vous à Skype entreprise Server dans votre réseau interne en tant que membre du groupe administrateurs locaux.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;point. Ouvrez le **menu Démarrer**, puis **Exécutez** (ou effectuez une **recherche** et **exécution** ), puis tapez les informations suivantes :
    
  ```console
  https://<NAME OF YOUR ISSUING CA SERVER>/certsrv
  ```

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Par exemple :
    
  ```console
  https://ca01/contoso.com/certsrv
  ```

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;c. Sur la page Web certsrv de l’autorité émettrice, sous **Sélectionner une tâche**, cliquez sur **Télécharger un certificat d’autorité de certification, une chaîne de certificats ou une LRC**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;intraveineux. Sous **Télécharger un certificat d’autorité de certification, une chaîne de certificats ou la liste de révocation des certificats**, cliquez sur **Télécharger la chaîne du certificat de l’Autorité de certification**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;version. Dans la boîte de dialogue **Téléchargement de fichier**, cliquez sur **Enregistrer**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;VI. Enregistrez le fichier. p7b sur le disque dur du serveur, puis copiez-le dans un dossier sur chaque serveur Edge.
    
### <a name="nbspnbspnbspb-export-using-mmc"></a>&nbsp;&nbsp;&nbsp;p. Exportation avec la console MMC

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ma. Vous pouvez exporter le certificat racine de l’autorité de certification à partir de tout ordinateur joint au domaine à l’aide de la console MMC. Sélectionnez **Démarrer** et **Exécuter** ou ouvrez **Recherche** et tapez **MMC** pour l’ouvrir.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;point. Dans la console MMC, cliquez sur **Fichier**, puis sur **Ajouter/supprimer un composant logiciel enfichable**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;c. Dans la boîte de dialogue **Ajouter ou supprimer des composants logiciels enfichables**, sélectionnez **Certificats**, puis cliquez sur **Ajouter**. Dans l’invite, sélectionnez **Compte d’ordinateur**, puis sur **Suivant**. Dans la boîte de dialogue **Sélectionner un ordinateur**, sélectionnez **Ordinateur local**. Cliquez sur **Terminer**, puis sur **OK**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;intraveineux. Développez **certificats (ordinateur local)**. Développez **autorités de certification racines de confiance**. Sélectionnez **certificats**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;version. Cliquez sur le certificat racine émis par votre autorité de certification. Cliquez avec le bouton droit sur le certificat, sélectionnez **Toutes les tâches** dans le menu, puis sélectionnez **Exporter**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;VI. L’**Assistant Exportation du certificat** s’affiche. Cliquez sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;VII. Dans la boîte de dialogue **Format du fichier d’exportation**, sélectionnez le format de l’exportation. L’option recommandée est **Standard de syntaxe de message cryptographique - Certificats PKCS #7 (P7b)**. Si tel est le cas, n’oubliez pas de cocher la case **inclure tous les certificats dans le chemin d’accès de certification si** cela est possible, car vous pouvez également exporter la chaîne de certificats, y compris le certificat de l’autorité de certification racine et les certificats intermédiaires. Cliquez sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;VIII. Dans la boîte de dialogue **Fichier à exporter**, dans l’entrée de nom de fichier, tapez un nom et un chemin d’accès de fichier (l’extension par défaut est .p7b) pour le certificat exporté. Si ce n’est pas le cas, cliquez sur le bouton **Parcourir** pour accéder à l’emplacement où vous voulez enregistrer le certificat exporté, puis nommez le certificat exporté ici. Cliquez sur **Enregistrer**, puis sur **suivant** lorsque vous êtes prêt.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;IX. Consultez le résumé de vos actions et cliquez sur **Terminer** pour achever l’exportation du certificat. Cliquez sur **OK** pour confirmer l’exportation.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;x.x.x.. Copiez le fichier. p7b sur chaque serveur Edge.
    
### <a name="2-import-the-ca-certification-chain"></a>2. importer la chaîne de certification de l’autorité de certification

&nbsp;&nbsp;&nbsp;un. Sur chaque serveur Edge, ouvrez la console MMC (cliquez sur **Démarrer** , **exécuter**ou **Rechercher**, puis tapez **MMC** pour l’ouvrir).
    
&nbsp;&nbsp;&nbsp;p. Dans le menu **Fichier**, cliquez sur **Ajouter/Supprimer un composant logiciel enfichable**, puis sur **Ajouter**.
    
&nbsp;&nbsp;&nbsp;m. Dans la boîte de dialogue **Ajouter ou supprimer des composants logiciels enfichables**, cliquez sur **Certificats**, puis sur **Ajouter**.
    
&nbsp;&nbsp;&nbsp;j. Dans la boîte de dialogue **Composant logiciel enfichable Certificats**, cliquez sur **Compte d’ordinateur**, puis sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;e. Dans la boîte de dialogue **Sélectionner un ordinateur**, assurez-vous que la case à cocher **Ordinateur local : (l’ordinateur sur lequel cette console s’exécute)** est activée, puis cliquez sur **Terminer**.
    
&nbsp;&nbsp;&nbsp;touche. Cliquez sur **Fermer**, puis sur **OK**.
    
&nbsp;&nbsp;&nbsp;grand. Dans l’arborescence de la console, développez **Certificats (ordinateur local)**, cliquez avec le bouton droit sur **Autorités de certification racines de confiance**, sélectionnez **Toutes les tâches**, puis cliquez sur **Importer**.
    
&nbsp;&nbsp;&nbsp;h. Dans l’Assistant qui s’affiche, dans la zone **Fichier à importer**, spécifiez le nom de fichier du certificat (nom attribué au fichier .p7b dans la section précédente). Cliquez sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;ma. Laissez la case d’option **Placer tous les certificats dans le magasin suivant comme autorités de certification racines approuvées** activée. Cliquez sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;j.-c. Consultez le résumé, puis cliquez sur **Terminer** pour finaliser l’importation.
    
&nbsp;&nbsp;&nbsp;k. Pour cela, vous devez effectuer cette opération pour chaque serveur Edge que vous déployez.
    
### <a name="3-create-the-certificate-request"></a>3. création de la demande de certificat

&nbsp;&nbsp;&nbsp;un. Ouvrez une session sur l’un de vos serveurs Edge, démarrez l’Assistant Déploiement, puis **cliquez sur** **exécuter** (ou **exécuter à nouveau**, si vous avez déjà exécuté cet Assistant) dans l’Assistant déploiement.
    
&nbsp;&nbsp;&nbsp;p. Dans la page **Demande de certificat**, assurez-vous que l’option **Certificat Edge interne** est sélectionnée, puis cliquez sur **Demande**.
    
&nbsp;&nbsp;&nbsp;m. Dans la page **demandes retardées ou immédiates** , sélectionnez **Envoyer immédiatement la demande à une autorité de certification en ligne** si vous avez accès à celle-ci à partir de votre environnement Edge, ou **Préparez la demande maintenant, mais envoyez-la ultérieurement** .
    
&nbsp;&nbsp;&nbsp;j. Dans la page **Fichier de demande de certificat**, saisissez le composant complet et le nom de fichier de l’emplacement où le fichier sera enregistré (par exemple, c:\SkypeInternalEdgeCert.cer). Cliquez sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;e. Dans la page **Spécifier un autre modèle de certificat**, pour utiliser un autre modèle que le modèle Serveur web par défaut, activez la case à cocher **Utiliser un autre modèle de certificat pour l’autorité de certification sélectionnée**. Autrement, ne faites rien.
    
&nbsp;&nbsp;&nbsp;touche. Dans la page Nom et paramètres de sécurité, procédez comme suit :
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ma. Dans **Nom convivial**, saisissez le nom complet du certificat (par exemple, Périmètre interne).
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;point. Dans **Longueur en bits**, sélectionnez la longueur exprimée en bits (la valeur par défaut est 2048, vous pouvez l’augmenter pour plus de sécurité, mais cela ralentit les performances).
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;c. Si vous avez besoin d’un certificat exportable, vous devez activer la case à cocher **Marquer la clé privée du certificat comme exportable**.
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;intraveineux. Cliquez sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;grand. Dans la page **Informations relatives à l’organisation**, entrez le nom de votre organisation et de votre unité d’organisation). Vous pouvez entrer votre division ou service (Informatique, par exemple).
    
&nbsp;&nbsp;&nbsp;h. Dans la page **Informations géographiques**, saisissez les informations d’emplacement.
    
&nbsp;&nbsp;&nbsp;ma. Dans la page **Nom du sujet/Autres noms du sujet**, l’Assistant renseigne automatiquement les informations.
    
&nbsp;&nbsp;&nbsp;j.-c. Dans la page **Configurer d’autres noms du sujet supplémentaires**, ajoutez les autres noms du sujet supplémentaires nécessaires.
    
&nbsp;&nbsp;&nbsp;k. Dans la page Résumé de la **demande** , repérez les informations de certificat qui vont être utilisées pour générer votre demande. Si vous devez apporter des modifications, revenez en arrière pour le faire.
    
&nbsp;&nbsp;&nbsp;compt. Cliquez sur **suivant** pour générer le fichier CSR que vous devez fournir à l’autorité de certification (vous pouvez également cliquer sur **afficher le journal** pour consulter le journal de la demande de certificat).
    
&nbsp;&nbsp;&nbsp;m. Une fois la demande générée, vous pouvez cliquer sur **Afficher** pour consulter le certificat et sur **Terminer** pour fermer la fenêtre. Le contenu du fichier CSR doit être affecté à votre autorité de certification afin qu’elle puisse générer un certificat que vous pourrez importer sur cet ordinateur dans la section suivante.
    

### <a name="4-import-the-certificate"></a>4. importer le certificat

&nbsp;&nbsp;&nbsp;un. Connectez-vous en tant que membre du groupe Administrateurs local au serveur Edge à partir duquel vous avez créé votre demande de certificat.
    
&nbsp;&nbsp;&nbsp;p. Dans l’Assistant Déploiement, à côté de l' **étape 3. Demandez, installez ou attribuez des certificats**, cliquez de **nouveau sur exécuter**.
    
&nbsp;&nbsp;&nbsp;m. Dans la page **Tâches se rapportant aux certificats disponibles**, cliquez sur **Importer un certificat à partir d’un fichier .P7b, .pfx ou .cer**.
    
&nbsp;&nbsp;&nbsp;j. Dans la page **Importer un certificat**, tapez le chemin complet et le nom du fichier du certificat que vous avez reçu dans la section précédent (ou cliquez sur **Parcourir** pour rechercher et sélectionner le fichier).
    
&nbsp;&nbsp;&nbsp;e. Si vous importez des certificats pour d’autres membres de votre pool Edge et que votre certificat contient une clé privée, veillez à sélectionner le **fichier de certificat contenant la clé privée du certificat** , puis à spécifier le mot de passe. Cliquez sur **Suivant** pour continuer.
    
&nbsp;&nbsp;&nbsp;touche. Dans la page**Résumé** , cliquez sur **suivant** une fois que vous avez confirmé les informations, puis **finissez** une fois que le certificat a été correctement importé.
    
 
### <a name="5-export-the-certificate"></a>5. exporter le certificat

&nbsp;&nbsp;&nbsp;un. Vérifiez que vous êtes connecté au serveur Edge sur lequel vous avez importé le certificat auparavant, en tant que membre du groupe administrateurs locaux.
    
&nbsp;&nbsp;&nbsp;p. Cliquez sur **Démarrer**, **exécuter** (ou ouvrir la **recherche** ) et tapez **MMC**.
    
&nbsp;&nbsp;&nbsp;m. Dans la console MMC, cliquez sur **Fichier**, puis sur **Ajouter/Supprimer un composant logiciel enfichable**.
    
&nbsp;&nbsp;&nbsp;j. Dans la boîte de dialogue **Ajouter ou supprimer des composants logiciels enfichables**, cliquez sur **Certificats**, puis sur **Ajouter**.
    
&nbsp;&nbsp;&nbsp;e. Dans la boîte de dialogue composant logiciel enfichable **certificats** , choisissez **compte d’ordinateur**. Cliquez sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;touche. Dans la boîte de dialogue **Sélectionner un ordinateur**, sélectionnez **Ordinateur local : (l’ordinateur sur lequel cette console s’exécute)**. Cliquez sur **Terminer**. La configuration de la console MMC est terminée.
    
&nbsp;&nbsp;&nbsp;grand. Double-cliquez sur **Certificats (ordinateur local)** pour développer les magasins de certificats. Double-cliquez sur **personnel**, puis sur **certificats**.
    
  > [!NOTE]
  > Il est possible que vous ne voyiez pas les certificats dans le magasin personnel de certificats de l’ordinateur local. Vous n’avez pas besoin d’effectuer une recherche, si la clé n’est pas disponible, cela signifie que le certificat importé n’a pas associé de clé privée. Essayez de demander et d’importer les étapes ci-dessus une fois de plus, et si vous êtes certain de vous être assuré, contactez votre administrateur ou votre fournisseur d’autorité de certification. 
  
&nbsp;&nbsp;&nbsp;h. Dans le **magasin personnel de certificats** de l’ordinateur local, cliquez avec le bouton droit sur le certificat que vous exportez. Sélectionnez **Toutes les tâches** dans le menu qui s’affiche, puis cliquez sur **Exporter**.
    
&nbsp;&nbsp;&nbsp;ma. Dans l’**Assistant Exportation du certificat**, cliquez sur **Suivant**. Sélectionnez **Oui, exporter la clé privée**. Cliquez sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;j.-c. Dans la boîte de dialogue **Exporter les formats de fichiers**, sélectionnez **Échange d’informations personnelles – PKCS#12 (.PFX)**, puis les éléments suivants :
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ma. Incluez tous les certificats dans le chemin d’accès de certification, si possible.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;point. Exportez toutes les propriétés étendues.
    
   > [!NOTE]
   > Ne sélectionnez **JAMAIS****Supprimer la clé privée si l’exportation s’est terminée correctement**. Cela signifie que vous devez réimporter le certificat et la clé privée vers ce serveur Edge.
  
&nbsp;&nbsp;&nbsp;k. Si vous souhaitez affecter un mot de passe pour protéger la clé privée, vous pouvez taper un mot de passe pour cette clé. Entrez de nouveau le mot de passe pour le confirmer, puis cliquez sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;compt. Tapez un chemin d’accès et un nom de fichier avec l’extension **.pfx** pour le certificat exporté. Le chemin d’accès doit être accessible par les autres serveurs de périphérie du pool, ou vous devez déplacer le fichier au moyen de médias externes (par exemple, un lecteur USB). Cliquez sur **suivant** lorsque vous avez effectué votre choix.
    
&nbsp;&nbsp;&nbsp;m. Consultez le résumé dans la boîte de dialogue **Fin de l’Assistant Exportation du certificat**, puis cliquez sur **Terminer**.
    
&nbsp;&nbsp;&nbsp;No. Cliquez sur **OK** dans la boîte de dialogue indiquant que l’exportation a abouti.
    
 
### <a name="6-assign-the-certificate"></a>6. affecter le certificat

&nbsp;&nbsp;&nbsp;un. Sur chaque serveur Edge, dans l’Assistant Déploiement, en regard de l' **étape 3. Demandez, installez ou attribuez des certificats**, cliquez de **nouveau sur exécuter**.
    
&nbsp;&nbsp;&nbsp;p. Dans la page **Tâches se rapportant aux certificats disponibles**, cliquez sur **Affecter un certificat existant**.
    
&nbsp;&nbsp;&nbsp;m. Dans la page **Affectation de certificat**, sélectionnez **Serveur Edge interne** dans la liste.
    
&nbsp;&nbsp;&nbsp;j. Dans la page **magasin de certificats** , sélectionnez le certificat que vous avez importé pour le bord interne (à partir de la section précédente).
    
&nbsp;&nbsp;&nbsp;e. Dans la page **Résumé de l’affectation du certificat**, vérifiez vos paramètres, puis cliquez sur **Suivant** pour affecter le certificat.
    
&nbsp;&nbsp;&nbsp;touche. Dans la page de fin de l’Assistant, cliquez sur **Terminer**.
    
&nbsp;&nbsp;&nbsp;grand. Une fois que vous avez terminé cette procédure, il est conseillé d’ouvrir le composant logiciel enfichable Certificats MMC sur chaque serveur Edge, de développer l’option **certificats (ordinateur local)**, de développer **personnel**, de cliquer sur **certificats**et de vérifier que le certificat de bord interne figure dans le volet Détails.
    
### <a name="external-edge-interface-certificates"></a>Certificats d’interface externe de serveur Edge

 
### <a name="1-create-the-certificate-request"></a>1. création de la demande de certificat

&nbsp;&nbsp;&nbsp;un. Ouvrez une session sur l’un de vos serveurs Edge, démarrez l’Assistant Déploiement, puis **cliquez sur exécuter** (ou **exécuter à nouveau**, si vous avez déjà exécuté cet Assistant) dans l’Assistant déploiement.
    
&nbsp;&nbsp;&nbsp;p. Dans la page **Tâches se rapportant aux certificats disponibles**, cliquez sur **Créer une demande de certificat**.
    
&nbsp;&nbsp;&nbsp;m. Dans la page **Demande de certificat**, assurez-vous que l’option **Certificat Edge externe** est sélectionnée, puis cliquez sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;j. Dans la page **Demandes différées ou immédiates**, cliquez sur **Préparer la demande, mais ne pas l’envoyer maintenant**.
    
&nbsp;&nbsp;&nbsp;e. Dans la page **Fichier de demande de certificat**, saisissez le composant complet et le nom de fichier de l’emplacement où le fichier sera enregistré (par exemple, c:\SkypeInternalEdgeCert.cer). Cliquez sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;touche. Dans la page **Spécifier un autre modèle de certificat**, pour utiliser un autre modèle que le modèle Serveur web par défaut, activez la case à cocher **Utiliser un autre modèle de certificat pour l’autorité de certification sélectionnée**.
    
&nbsp;&nbsp;&nbsp;grand. Dans la page Nom et paramètres de sécurité, procédez comme suit :
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ma. Dans **Nom convivial**, saisissez le nom complet du certificat (par exemple, Périmètre externe).
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;point. Dans **Longueur en bits**, sélectionnez la longueur exprimée en bits (la valeur par défaut est 2048, vous pouvez l’augmenter pour plus de sécurité, mais cela ralentit les performances).
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;c. Si vous avez besoin d’un certificat exportable, vous devez activer la case à cocher **Marquer la clé privée du certificat comme exportable**.
    
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;intraveineux. Cliquez sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;h. Dans la page **Informations relatives à l’organisation**, entrez le nom de votre organisation et de votre unité d’organisation). Vous pouvez entrer votre division ou service (Informatique, par exemple).
    
&nbsp;&nbsp;&nbsp;ma. Dans la page **Informations géographiques**, saisissez les informations d’emplacement.
    
&nbsp;&nbsp;&nbsp;j.-c. Dans la page **Nom du sujet/Autres noms du sujet**, l’Assistant renseigne automatiquement les informations nécessaires.
    
&nbsp;&nbsp;&nbsp;k. Sur le **paramètre de domaine SIP sur la page autres noms d’objet (sans)** , activez la case à cocher domaine pour ajouter un SIP.<sipdomain> entrée de la liste autres noms d’objet.
    
&nbsp;&nbsp;&nbsp;compt. Dans la page **Configurer d’autres noms du sujet supplémentaires**, ajoutez les autres noms du sujet supplémentaires nécessaires.
    
&nbsp;&nbsp;&nbsp;m. Dans la page Résumé de la **demande** , repérez les informations de certificat qui vont être utilisées pour générer votre demande. Si vous devez apporter des modifications, revenez en arrière pour le faire.
    
&nbsp;&nbsp;&nbsp;No. Lorsque vous êtes prêt, cliquez sur **suivant** pour générer le fichier CSR que vous devez fournir à l’autorité de certification (vous pouvez également cliquer sur **afficher le journal** pour consulter le journal de la demande de certificat).
    
&nbsp;&nbsp;&nbsp;ô. Une fois la demande générée, vous pouvez cliquer sur **Afficher** pour consulter le certificat et sur **Terminer** pour fermer la fenêtre. Le contenu du fichier CSR doit être affecté à votre autorité de certification afin qu’elle puisse générer un certificat que vous pourrez importer sur cet ordinateur dans la section suivante.
    
&nbsp;&nbsp;&nbsp;DL. (FACULTATIF) Il est possible que vous soyez invité à fournir certaines informations lors de l’envoi de la demande de signature de certificat (CSR), comme suit (les autorités de certification varient considérablement, de sorte que ce n’est peut-être pas obligatoire) :
    
  - **Microsoft** comme plateforme serveur
    
  - **Services Internet (IIS)** comme version
    
  - **Serveur web** comme type d’utilisation
    
  - **PKCS7** comme réponse
    
 
### <a name="2-import-the-certificate"></a>2. importer le certificat

&nbsp;&nbsp;&nbsp;un. Connectez-vous en tant que membre du groupe Administrateurs local au serveur Edge à partir duquel vous avez créé votre demande de certificat.
    
&nbsp;&nbsp;&nbsp;p. Dans l’Assistant Déploiement, à côté de l' **étape 3. Demandez, installez ou attribuez des certificats**, cliquez de **nouveau sur exécuter**.
    
&nbsp;&nbsp;&nbsp;m. Dans la page **Tâches se rapportant aux certificats disponibles**, cliquez sur **Importer un certificat à partir d’un fichier .P7b, .pfx ou .cer**.
    
&nbsp;&nbsp;&nbsp;j. Dans la page **Importer un certificat**, tapez le chemin complet et le nom du fichier du certificat que vous avez reçu dans la section précédent (ou cliquez sur **Parcourir** pour rechercher et sélectionner le fichier). Si votre certificat contient une clé privée, veillez à sélectionner le **fichier de certificat contenant la clé privée du certificat**, puis entrez le mot de passe de la clé privée. Cliquez sur **Suivant** pour continuer.
    
&nbsp;&nbsp;&nbsp;e. Dans la page **Importer le résumé du certificat**, vérifiez les informations résumées, puis cliquez sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;touche. Sur la page **exécution des commandes** , vous pouvez examiner le résultat de l’importation une fois qu’il est terminé, cliquez sur Afficher le **Journal**. Cliquez sur **Terminer** pour terminer l’importation du certificat.
    
&nbsp;&nbsp;&nbsp;grand. Si vous avez d’autres serveurs Edge dans un pool, vous devez suivre également les deux procédures suivantes. S’il s’agit d’un serveur Edge autonome, vous avez terminé avec les certificats externes.
    
 
### <a name="3-export-the-certificate"></a>3. exporter le certificat

&nbsp;&nbsp;&nbsp;un. Vérifiez que vous êtes connecté au serveur Edge sur lequel vous avez importé le certificat en tant qu’administrateur local.
    
&nbsp;&nbsp;&nbsp;p. Cliquez sur **Démarrer**, **exécuter** (ou ouvrir la **recherche** ) et tapez **MMC**.
    
&nbsp;&nbsp;&nbsp;m. Dans la console MMC, cliquez sur **Fichier**, puis sur **Ajouter/Supprimer un composant logiciel enfichable**.
    
&nbsp;&nbsp;&nbsp;j. Dans la boîte de dialogue **Ajouter ou supprimer des composants logiciels enfichables**, cliquez sur **Certificats**, puis sur **Ajouter**.
    
&nbsp;&nbsp;&nbsp;e. Dans la boîte de dialogue composant logiciel enfichable **certificats** , choisissez **compte d’ordinateur**. Cliquez sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;touche. Dans la boîte de dialogue **Sélectionner un ordinateur**, sélectionnez **Ordinateur local : (l’ordinateur sur lequel cette console s’exécute)**. Cliquez sur **Terminer**. La configuration de la console MMC est terminée.
    
&nbsp;&nbsp;&nbsp;grand. Double-cliquez sur **Certificats (ordinateur local)** pour développer les magasins de certificats. Double-cliquez sur **Personnel**, puis sur **Certificats**.
    
   > [!NOTE]
   > Il est possible que vous ne voyiez pas les certificats dans le magasin personnel de certificats de l’ordinateur local. Vous n’avez pas besoin d’effectuer une recherche, si la clé n’est pas disponible, cela signifie que le certificat importé n’a pas associé de clé privée. Essayez de demander et d’importer les étapes ci-dessus une fois de plus, et si vous êtes certain de vous être assuré, contactez votre administrateur ou votre fournisseur d’autorité de certification. 
  
&nbsp;&nbsp;&nbsp;h. Dans le **magasin personnel de certificats** de l’ordinateur local, cliquez avec le bouton droit sur le certificat que vous exportez. Sélectionnez **Toutes les tâches** dans le menu qui s’affiche, puis cliquez sur **Exporter**.
    
&nbsp;&nbsp;&nbsp;ma. Dans l’**Assistant Exportation du certificat**, cliquez sur **Suivant**. Sélectionnez **Oui, exporter la clé privée**. Cliquez sur **Suivant**.
    
   > [!NOTE]
   > Si **Oui, exporter la clé privée** n’est pas disponible, la clé privée de ce certificat n’a pas été marquée en vue d’une exportation avant que vous ne l’ayez obtenu. Pour pouvoir poursuivre l’exportation, vous devez faire une nouvelle demande de certificat auprès du fournisseur en vous assurant que le certificat est marqué pour l’exportation.
  
&nbsp;&nbsp;&nbsp;j.-c. Dans la boîte de dialogue Exporter les formats de fichiers, sélectionnez Échange d’informations personnelles – PKCS#12 (.PFX), puis les éléments suivants :
    
 &nbsp;&nbsp;&nbsp;ma. Incluez tous les certificats dans le chemin d’accès de certification, si possible.
    
 &nbsp;&nbsp;&nbsp;point. Exportez toutes les propriétés étendues.
    
   > [!NOTE]
   > Ne sélectionnez **JAMAIS****Supprimer la clé privée si l’exportation s’est terminée correctement**. Cela signifie que vous devez réimporter le certificat et la clé privée vers ce serveur Edge.
  
&nbsp;&nbsp;&nbsp;k. Si vous souhaitez affecter un mot de passe pour protéger la clé privée, vous pouvez taper un mot de passe pour cette clé. Entrez de nouveau le mot de passe pour le confirmer, puis cliquez sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;compt. Tapez un chemin d’accès et un nom de fichier avec l’extension **.pfx** pour le certificat exporté. Le chemin d’accès doit être accessible par les autres serveurs de périphérie du pool, ou vous devez déplacer le fichier au moyen de médias externes (par exemple, un lecteur USB). Cliquez sur **suivant** lorsque vous avez effectué votre choix.
    
&nbsp;&nbsp;&nbsp;m. Consultez le résumé dans la boîte de dialogue **Fin de l’Assistant Exportation du certificat**, puis cliquez sur **Terminer**.
    
&nbsp;&nbsp;&nbsp;No. Cliquez sur **OK** dans la boîte de dialogue indiquant que l’exportation a abouti.
    
&nbsp;&nbsp;&nbsp;ô. Vous devez à présent revenir à la section importer le certificat antérieurement et importer le certificat sur tous vos serveurs de frontière restants, puis procéder à l’attribution.
    
 
### <a name="4-assign-the-certificate"></a>4. affecter le certificat

&nbsp;&nbsp;&nbsp;un. Sur **chaque** serveur Edge, dans l’Assistant Déploiement, en regard de l' **étape 3. Demandez, installez ou attribuez des certificats**, cliquez de **nouveau sur exécuter**.
    
&nbsp;&nbsp;&nbsp;p. Dans la page **Tâches se rapportant aux certificats disponibles**, cliquez sur **Affecter un certificat existant**.
    
&nbsp;&nbsp;&nbsp;m. Dans la page **affectation de certificat** , sélectionnez **bordure externe** dans la liste.
    
&nbsp;&nbsp;&nbsp;j. Dans la page **magasin de certificats** , sélectionnez le certificat que vous avez importé pour le bord externe (à partir de la section précédente).
    
&nbsp;&nbsp;&nbsp;e. Dans la page **Résumé de l’affectation du certificat**, vérifiez vos paramètres, puis cliquez sur **Suivant** pour affecter le certificat.
    
&nbsp;&nbsp;&nbsp;touche. Dans la page de fin de l’Assistant, cliquez sur **Terminer**.
    
&nbsp;&nbsp;&nbsp;grand. Une fois que vous avez terminé cette procédure, il est préférable d’ouvrir le composant logiciel enfichable Certificats MMC sur chaque serveur, de développer **certificats (ordinateur local)**, de **personnaliser**le mode de certification, de cliquer sur **certificats**et de vérifier que le certificat de bord interne figure dans le volet Détails.
    
   > [!NOTE]
   > Vous devez également configurer les certificats pour votre serveur de proxy inverse. 
  
## <a name="starting-the-edge-servers"></a>Démarrage des serveurs de périphérie

Une fois l’installation terminée, vous devez démarrer les services sur chaque serveur Edge dans votre déploiement :
  
1. Sur chaque serveur Edge, dans l' **Assistant Déploiement**, en regard de l' **étape 4 : démarrer les services**, cliquez sur **exécuter**.
    
2. Dans la page **Démarrer les services Skype entreprise Server** , examinez la liste des services, puis cliquez sur **suivant** pour démarrer les services.
    
3. Une fois les services lancés, cliquez sur **Terminer** pour fermer l’Assistant.
    
4. (Facultatif) Toujours sous l’**Étape 4 : Lancement des services**, cliquez sur **État des services**.
    
5.  Dans la **console MMC Services** sur chaque serveur, vérifiez que tous les services Skype entreprise Server sont en cours d’exécution.
    

