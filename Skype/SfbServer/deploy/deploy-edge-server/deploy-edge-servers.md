---
title: Déployer des serveurs Edge dans Skype Entreprise Server
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
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 63c7251c-080a-4175-99a6-f86d0266d6bc
description: 'Résumé : Découvrez comment déployer des serveurs Edge dans votre environnement Skype Entreprise Server web.'
ms.openlocfilehash: 30beb7b42b2f77e82d83768d918102cbaa0f7f5e
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60852728"
---
# <a name="deploy-edge-servers-in-skype-for-business-server"></a>Déployer des serveurs Edge dans Skype Entreprise Server
 
**Résumé :** Découvrez comment déployer des serveurs Edge dans votre environnement Skype Entreprise Server web.
  
Les sections suivantes contiennent les étapes qui sont destinées à être suivies après la révision de la documentation Skype Entreprise Server plan pour les [déploiements](../../plan-your-deployment/edge-server-deployments/edge-server-deployments.md) de serveurs Edge dans Skype Entreprise Server documentation. Les étapes de déploiement sont les suivantes :
  
- Interfaces réseau
    
- Installation
    
- Certificats
    
- Démarrage des serveurs Edge
    
## <a name="network-interfaces"></a>Interfaces réseau

Comme indiqué dans la planification, vous allez configurer votre interface réseau avec DNS dans le réseau de périmètre hébergeant vos serveurs Edge ou sans DNS dans le réseau de périmètre.
  
### <a name="interface-configuration-with-dns-servers-in-the-perimeter-network"></a>Configuration de l’interface avec les serveurs DNS dans le réseau de périmètre

1. Installez deux cartes réseau pour chaque serveur Edge, une pour l’interface interne et une pour l’interface externe.
    
    > [!NOTE]
    > Les sous-réseaux internes et externes ne doivent pas être routables entre eux. 
  
2. Sur votre interface externe, vous allez configurer l’une **des** opérations suivantes :
    
   a. Trois adresses IP statiques sur le sous-réseau du réseau de périmètre externe et pointent la passerelle par défaut vers l’interface interne du pare-feu externe. Configurez les paramètres DNS de la carte pour qu’ils pointent vers une paire de serveurs DNS de périmètre.
    
   b. Une adresse IP statique sur le sous-réseau du réseau de périmètre externe et pointer la passerelle par défaut vers l’interface interne du pare-feu externe. Configurez les paramètres DNS de la carte pour qu’ils pointent vers une paire de serveurs DNS de périmètre. Cette configuration n’est acceptable que si vous avez précédemment configuré votre topologie pour qu’elle présente des valeurs non standard dans les affectations de ports, ce qui est décrit dans l’article Créer votre topologie Edge pour [Skype Entreprise Server.](create-your-edge-topology.md)
    
3. Sur votre interface interne, configurez une adresse IP statique sur le sous-réseau du réseau de périmètre interne et ne définissez pas de passerelle par défaut. Configurez les paramètres DNS de l’adaptateur pour qu’ils pointent vers au moins un serveur DNS, mais de préférence une paire de serveurs DNS de périmètre.
    
4. Créez des itinéraires statiques persistants sur l’interface interne vers tous les réseaux internes où résident les clients, Skype Entreprise Server et Exchange serveurs de messagerie unifiée.
    
### <a name="interface-configuration-without-dns-servers-in-the-perimeter-network"></a>Configuration de l’interface sans serveurs DNS dans le réseau de périmètre

1. Installez deux cartes réseau pour chaque serveur Edge, une pour l’interface interne et une pour l’interface externe.
    
    > [!NOTE]
    > Les sous-réseaux internes et externes ne doivent pas être routables entre eux. 
  
2. Sur votre interface externe, vous allez configurer l’une **des** opérations suivantes :
    
   a. Trois adresses IP statiques sur le sous-réseau du réseau de périmètre externe. Vous devez également configurer la passerelle par défaut sur l’interface externe, par exemple en définissant le routeur côté Internet ou le pare-feu externe comme passerelle par défaut. Configurez les paramètres DNS de la carte pour qu’ils pointent vers un serveur DNS externe, idéalement une paire de serveurs DNS externes.
    
   b. Une adresse IP statique sur le sous-réseau du réseau de périmètre externe. Vous devez également configurer la passerelle par défaut sur l’interface externe, par exemple en définissant le routeur côté Internet ou le pare-feu externe comme passerelle par défaut. Configurez les paramètres DNS de la carte pour qu’ils pointent vers un serveur DNS externe, ou dans l’idéal une paire de serveurs DNS externes. Cette configuration n’est acceptable que si vous avez précédemment configuré votre topologie pour qu’elle présente des valeurs non standard dans les affectations de ports, ce qui est décrit dans l’article Créer votre topologie Edge pour [Skype Entreprise Server.](create-your-edge-topology.md)
    
3. Sur votre interface interne, configurez une adresse IP statique sur le sous-réseau du réseau de périmètre interne et ne définissez pas de passerelle par défaut. Laissez également les paramètres DNS de l’adaptateur vides.
    
4. Créez des itinéraires statiques persistants sur l’interface interne vers tous les réseaux internes où résident les clients, Skype Entreprise Server et Exchange serveurs de messagerie unifiée.
    
5. Modifiez le fichier HOST sur chaque serveur Edge pour contenir un enregistrement pour le serveur du saut suivant ou l’adresse IP virtuelle (VIP). Cet enregistrement sera le directeur, Édition Standard serveur ou pool frontal que vous avez configuré en tant qu’adresse de saut suivant du serveur Edge dans le Générateur de topologie. Si vous utilisez l’équilibrage de charge DNS, incluez une ligne pour chaque membre du pool du saut suivant.
    
## <a name="installation"></a>Installation

Pour effectuer ces étapes correctement, vous devez avoir suivi les étapes de l’article Créer votre topologie [Edge pour Skype Entreprise Server](create-your-edge-topology.md) article.
  
1. Connectez-vous au serveur que vous avez configuré pour le rôle serveur Edge avec un compte du groupe Administrateur local.
    
2. Vous aurez besoin du fichier de configuration de topologie que vous avez copié à la fin de la documentation sur la topologie du serveur Edge sur cet ordinateur. Accédez au support externe sur qui vous avez placé ce fichier de configuration (comme un lecteur USB ou un partage).
    
3. Démarrez **l’Assistant Déploiement.**
    
4. Une fois l’Assistant ouvert, cliquez sur Installer ou mettre **à jour Skype Entreprise Server système.**
    
5. L’Assistant exécute des vérifications pour voir si quelque chose est déjà installé. Comme il s’agit de la première exécution de l’Assistant, vous pouvez commencer à **l’étape 1. Installez le magasin de configurations local.**
    
6. La **boîte de dialogue Configurer le réplica local du magasin central de** gestion s’affiche. Vous devez cliquer sur **Importer à partir d’un fichier (recommandé pour les serveurs Edge).**
    
7. À partir de là, accédez à l’emplacement de la topologie que vous avez exportée précédemment, sélectionnez le fichier .zip, cliquez sur **Ouvrir,** puis sur **Suivant**.
    
8. L’Assistant Déploiement lit le fichier de configuration et écrit le fichier de configuration XML sur l’ordinateur local.
    
9. Une fois que le processus **Exécution de commandes** est terminé, cliquez sur **Terminer**.
    
10. Dans l’Assistant Déploiement, cliquez sur **Étape 2. Installer ou supprimer Skype Entreprise Server composants.** L’Assistant installe ensuite les Skype Entreprise Server Edge spécifiés dans le fichier de configuration XML qui a été stocké sur l’ordinateur local.
    
11. Une fois l’installation terminée, vous pouvez passer aux étapes de la section **Certificats ci-dessous.**
    
## <a name="certificates"></a>Certificats

Les certificats requis pour le serveur Edge se trouvent dans la documentation de planification des certificats Edge. Les étapes de configuration des certificats sont ci-dessous.
  
> [!NOTE]
> Lorsque vous exécutez l’Assistant Certificat, vous devez être connecté en tant que compte avec les autorisations correctes pour le type de modèle de certificat que vous allez utiliser. Par défaut, une demande Skype Entreprise Server certificat va utiliser le modèle de certificat serveur Web. Si vous êtes connecté avec un compte membre du groupe RTCUniversalServerAdmins pour demander un certificat via ce modèle, vérifiez que le groupe a reçu les autorisations d’inscription pour utiliser ce modèle. 
  
### <a name="internal-edge-interface-certificates"></a>Certificats de l’interface Edge interne

 
### <a name="1-download-or-export-the-ca-certification-chain"></a>1. Télécharger ou exporter la chaîne de certification de l’ac.

 
#### <a name="nbspnbspnbsp-a-download-using-certsrv-web-site"></a>&nbsp;&nbsp;&nbsp; a. Télécharger à l’aide du site web certsrv

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;i. Connectez-vous à Skype Entreprise Server votre réseau interne en tant que membre du groupe Administrateurs local.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ii. Ouvrez **Démarrer** et **Exécuter** (ou **Rechercher** et **exécuter),** puis tapez ce qui suit :
    
  ```console
  https://<NAME OF YOUR ISSUING CA SERVER>/certsrv
  ```

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Par exemple :
    
  ```console
  https://ca01/contoso.com/certsrv
  ```

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iii. Sur la page web certsrv de l’ac émettrice, sous Sélectionner une **tâche,** cliquez sur Télécharger un certificat d’ac, une chaîne de **certificats ou une CRL.**
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iv. Sous **Télécharger un certificat d’ac, une chaîne de certificats ou une CRL,** cliquez sur Télécharger la chaîne de **certificats de l’ac.**
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;v. Dans la **zone de téléchargement de** fichier, cliquez sur **Enregistrer.**
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;vi. Enregistrez le fichier .p7b sur le disque dur sur le serveur, puis copiez-le dans un dossier sur chacun de vos serveurs Edge.
    
### <a name="nbspnbspnbspb-export-using-mmc"></a>&nbsp;&nbsp;&nbsp;b. Exporter à l’aide de MMC

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;i. Vous pouvez exporter le certificat racine de l’ac à partir de n’importe quel ordinateur joint au domaine à l’aide de la MMC. Go to **Start** and **Run**, or open **Search**, and type **MMC** to open.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ii. Dans la console MMC, cliquez sur **Fichier,** puis sur **Ajouter/Supprimer un logiciel en snap-in**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iii. Dans la **boîte de dialogue Ajouter ou supprimer des logiciels** en un clin d’œil, choisissez **Certificats,** puis cliquez sur **Ajouter**. Lorsque vous y invitez, **sélectionnez Compte d’ordinateur,** puis **Suivant**. Dans la **boîte de dialogue Sélectionner un** ordinateur, sélectionnez Ordinateur **local.** Cliquez **sur** Terminer, puis **sur OK.**
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;iv. Développer **les certificats (ordinateur local)**. Développez **Autorités de certification racines de confiance**. Sélectionnez **Certificats.**
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;v. Cliquez sur le certificat racine émis par votre ca. Cliquez avec le bouton droit sur le certificat, choisissez **Toutes les** tâches dans le menu, puis sélectionnez **Exporter.**
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;vi. **L’Assistant Exportation de** certificat s’ouvre. Cliquez sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;vii. Dans la **boîte de dialogue Exporter le format de** fichier, sélectionnez le format vers le format vers qui vous souhaitez exporter. Notre recommandation est la norme de syntaxe de message de chiffrement **- Certificats PKCS #7 (P7b).** Si c’est également votre choix, n’oubliez pas de cocher inclure tous les certificats dans le chemin d’accès de certification si **possible,** car cela permet également d’exporter la chaîne de certificats, y compris le certificat d’ac racine et les certificats intermédiaires. Cliquez sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;viii. Dans la **boîte de** dialogue Fichier à exporter, dans l’entrée du nom de fichier, tapez un chemin d’accès et un nom de fichier (l’extension par défaut serait .p7b) pour le certificat exporté. Si c’est plus facile  pour vous, cliquez sur le bouton Parcourir pour aller à l’emplacement où vous souhaitez enregistrer le certificat exporté et nommez le certificat exporté ici. Cliquez **sur** Enregistrer, puis **sur Suivant** lorsque vous êtes prêt.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ix. Consultez le résumé de vos actions, puis cliquez sur **Terminer** pour terminer l’exportation du certificat. Cliquez **sur OK** pour confirmer l’exportation réussie.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;x. Copiez le fichier .p7b sur chacun de vos serveurs Edge.
    
### <a name="2-import-the-ca-certification-chain"></a>2. Importer la chaîne de certification DE L’AC

&nbsp;&nbsp;&nbsp;a. Sur chaque serveur Edge, ouvrez la MMC **(choisissez** Démarrer **et** exécuter ou **Rechercher,** puis tapez **MMC** à ouvrir).
    
&nbsp;&nbsp;&nbsp;b. Dans le menu **Fichier,** cliquez sur **Ajouter/Supprimer un logiciel en snap-in,** puis choisissez **Ajouter**.
    
&nbsp;&nbsp;&nbsp;c. Dans la **zone Ajouter ou supprimer des logiciels** en un clin d’œil, cliquez sur **Certificats,** puis cliquez sur **Ajouter.**
    
&nbsp;&nbsp;&nbsp;d. Dans la boîte de dialogue **Composant logiciel enfichable Certificats**, cliquez sur **Compte d’ordinateur**, puis sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;e. Dans la **boîte de** dialogue Sélectionner un ordinateur, assurez-vous que la case à cocher Ordinateur local : (l’ordinateur sur qui cette console est en cours d’exécution) est cocher, puis cliquez sur **Terminer**. 
    
&nbsp;&nbsp;&nbsp;f. Cliquez **sur Fermer,** puis **SUR OK.**
    
&nbsp;&nbsp;&nbsp;g. Dans l’arborescence de la console, développez **Certificats (ordinateur local),** cliquez avec le bouton droit sur Autorités de **certification** racines de confiance, allez à Toutes les **tâches,** puis cliquez sur **Importer**.
    
&nbsp;&nbsp;&nbsp;h. Dans l’Assistant qui  s’affiche, dans la boîte de texte Fichier à importer, spécifiez le nom de fichier du certificat (le nom que vous avez donné au fichier .p7b dans la section précédente). Cliquez sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;i. Laissez la radio sur **Placer tous les certificats** dans le magasin suivant, car les autorités de certification racines de confiance doivent être sélectionnées. Cliquez sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;j. Consultez le résumé, puis cliquez sur **Terminer** pour terminer l’importation.
    
&nbsp;&nbsp;&nbsp;k. Cette étape doit être effectuée pour chaque serveur Edge que vous déployez.
    
### <a name="3-create-the-certificate-request"></a>3. Créer la demande de certificat

&nbsp;&nbsp;&nbsp;a. Connectez-vous à l’un de vos serveurs Edge, démarrez l’Assistant Déploiement, puis à l’étape 3 : Demander, installer ou attribuer des **certificats,** cliquez sur Exécuter **(ou** exécuter à **nouveau,** si vous avez déjà exécuté cet Assistant).
    
&nbsp;&nbsp;&nbsp;b. Dans la page **Demande de** certificat, assurez-vous que le certificat **Edge** interne est sélectionné, puis cliquez sur **Demander**.
    
&nbsp;&nbsp;&nbsp;c. Dans la **page** Demandes différées ou immédiates, sélectionnez Envoyer la demande immédiatement à une autorité de **certification** en ligne si vous avez accès à une demande à partir de votre environnement Edge, ou préparez la demande **maintenant,** mais envoyez-la ultérieurement.
    
&nbsp;&nbsp;&nbsp;d. Dans **la** page Fichier de demande de certificat, entrez la partie complète et le nom de fichier pour l’endroit où le fichier sera enregistré (par exemple, c:\SkypeInternalEdgeCert.cer). Cliquez sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;e. Dans **la** page Spécifier un autre modèle de certificat, pour utiliser  un autre modèle que le modèle WebServer par défaut, cochez la case Utiliser un autre modèle de certificat pour la case à cocher Autorité de certification sélectionnée. Sinon, ne rien faire.
    
&nbsp;&nbsp;&nbsp;f. Dans la page Nom et paramètres de sécurité, procédez comme suit :
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   i. Dans **le nom convivial,** entrez un nom complet pour le certificat (par exemple, Edge interne).
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  ii. En **longueur de bit,** choisissez votre longueur de bit (la valeur par défaut est 2048, vous pouvez aller plus haut et être plus sécurisé, mais cela ralentit les performances).
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  iii. Si vous avez besoin d’un certificat exportable, vous devez cocher la case à cocher Marquer la clé privée du certificat comme **exportable.**
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  iv. Cliquez sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;g. Dans la page **Informations sur l’organisation,** entrez le nom de votre organisation et de votre unité d’organisation. Vous pouvez entrer votre service ou service (informatique, par exemple).
    
&nbsp;&nbsp;&nbsp;h. Dans la page **Informations géographiques,** entrez vos informations d’emplacement.
    
&nbsp;&nbsp;&nbsp;i. Dans la page **Nom du sujet/Autres noms du** sujet, ce nom doit être rempli automatiquement par l’Assistant.
    
&nbsp;&nbsp;&nbsp;j. Dans la page **Configurer d’autres noms** du sujet supplémentaires, vous devez ajouter d’autres noms de sujet supplémentaires dont vous avez besoin.
    
&nbsp;&nbsp;&nbsp;k. Dans la page **Résumé de la** demande, regardez les informations de certificat qui seront utilisées pour générer votre demande. Si vous devez apporter des modifications, revenir en arrière et le faire maintenant.
    
&nbsp;&nbsp;&nbsp;l. Cliquez ensuite sur **Suivant** pour générer le fichier CSR que vous  devrez fournir à l’ac (vous pouvez également cliquer sur Afficher le journal pour consulter le journal de la demande de certificat).
    
&nbsp;&nbsp;&nbsp;m. Une fois la demande générée, vous pouvez cliquer sur  **Afficher** pour examiner le certificat et terminer pour fermer la fenêtre. Le contenu du fichier CSR doit être attribué à votre ca, afin qu’il puisse générer un certificat que vous pourrez importer sur cet ordinateur dans la section suivante.
    

### <a name="4-import-the-certificate"></a>4. Importer le certificat

&nbsp;&nbsp;&nbsp;a. Log on, as a member of the local Administrators group, to the Edge Server you made your certificate request from in the last procedure.
    
&nbsp;&nbsp;&nbsp;b. Dans l’Assistant Déploiement, à côté de **l’étape 3. Demander, installer ou attribuer des certificats,** cliquez **sur Exécuter à nouveau.**
    
&nbsp;&nbsp;&nbsp;c. Dans la page **Tâches de certificats disponibles,** cliquez sur **Importer un certificat à partir d’un . Fichier P7b, .pfx ou .cer**.
    
&nbsp;&nbsp;&nbsp;d. Dans la page **Importer** un certificat, tapez le chemin d’accès complet et  le nom de fichier du certificat que vous avez obtenu dans la section précédente (ou vous pouvez cliquer sur Parcourir pour rechercher et choisir le fichier de cette façon).
    
&nbsp;&nbsp;&nbsp;e. Si vous importez des certificats pour **d’autres** membres de votre pool edge et que votre certificat contient une clé privée, n’oubliez pas de cocher le fichier certificat qui contient la clé privée du certificat et de spécifier le mot de passe. Cliquez sur **Suivant** pour continuer.
    
&nbsp;&nbsp;&nbsp;f. Dans la page **Résumé,** cliquez sur **Suivant** une fois que vous avez confirmé les informations, puis terminez **l’importation** du certificat.
    
 
### <a name="5-export-the-certificate"></a>5. Exporter le certificat

&nbsp;&nbsp;&nbsp;a. Assurez-vous d’avoir ouvert une session sur le serveur Edge sur qui vous avez importé le certificat précédemment, en tant que membre du groupe Administrateurs local.
    
&nbsp;&nbsp;&nbsp;b. Cliquez **sur Démarrer,** **Exécuter** (ou **ouvrir la** recherche), puis **tapez MMC**.
    
&nbsp;&nbsp;&nbsp;c. Dans la console MMC, cliquez sur **Fichier,** puis sur **Ajouter/Supprimer un logiciel en snap-in**.
    
&nbsp;&nbsp;&nbsp;d. Dans la zone Ajouter ou supprimer des logiciels en **snap-in,** cliquez sur **Certificats,** puis cliquez sur **Ajouter**.
    
&nbsp;&nbsp;&nbsp;e. Dans la **boîte de dialogue Certificats** en ligne, sélectionnez **Compte d’ordinateur.** Cliquez sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;f. Dans la **boîte de dialogue** Sélectionner un ordinateur, **sélectionnez Ordinateur local : (l’ordinateur sur qui cette console s’exécute).** Cliquez sur **Terminer**. Cliquez **sur OK** et la configuration de la console MMC est terminée.
    
&nbsp;&nbsp;&nbsp;g. Double-cliquez **sur Certificats (ordinateur local)** pour développer les magasins de certificats. Double-cliquez **sur Personnel,** puis cliquez **sur Certificats.**
    
  > [!NOTE]
  > Vous êtes peut-être là et vous ne voyez aucun certificat dans le magasin personnel de certificats pour l’ordinateur local. Vous n’avez pas besoin de vous déplacer, si la clé n’est pas là, aucune clé privée n’est associée au certificat importé. Essayez les étapes de demande et d’importation ci-dessus une fois de plus, et si vous êtes sûr d’avoir tout ce qu’il faut, demandez à votre administrateur d’ac ou fournisseur. 
  
&nbsp;&nbsp;&nbsp;h. Dans le **magasin personnel de certificats** de l’ordinateur local, cliquez avec le bouton droit sur le certificat que vous exportez. Sélectionnez **toutes les** tâches dans le menu résultant, puis cliquez sur **Exporter.**
    
&nbsp;&nbsp;&nbsp;i. Dans l’**Assistant Exportation de certificat**, cliquez sur **Suivant**. Sélectionnez **Oui, exporter la clé privée.** Cliquez sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;j. Dans la **boîte de dialogue Exporter les formats** de fichiers, sélectionnez Informations Exchange - **PKCS#12 (. PFX),** puis sélectionnez ce qui suit :
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   i. Incluez tous les certificats dans le chemin d’accès de certification, si possible.
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   ii. Exporter toutes les propriétés étendues.
    
   > [!NOTE]
   > **NE** **SÉLECTIONNEZ JAMAIS Supprimer la clé privée si l’exportation a réussi.** Cela signifie que vous devez réimporter le certificat et la clé privée vers ce serveur Edge.
  
&nbsp;&nbsp;&nbsp;k. Si vous souhaitez attribuer un mot de passe pour protéger la clé privée, vous pouvez taper un mot de passe pour la clé privée. Reentez le mot de passe pour confirmer, puis cliquez sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;l. Tapez un chemin d’accès et un nom de fichier pour le certificat exporté, à l’aide de l’extension **de fichier .pfx**. Le chemin d’accès doit être accessible par les autres serveurs Edge du pool, ou vous devez déplacer le fichier au moyen d’un support externe (par exemple, un lecteur USB). Cliquez **sur Suivant** lorsque vous avez fait votre choix.
    
&nbsp;&nbsp;&nbsp;m. Consultez le résumé de la boîte de dialogue Fin de l’Assistant **Exportation de** certificat, puis cliquez sur **Terminer.**
    
&nbsp;&nbsp;&nbsp;n. Cliquez **sur OK** dans la boîte de dialogue d’exportation réussie.
    
 
### <a name="6-assign-the-certificate"></a>6. Affecter le certificat

&nbsp;&nbsp;&nbsp;a. Sur chaque serveur Edge, dans l’Assistant Déploiement, à côté de **l’étape 3. Demander, installer ou attribuer des certificats,** cliquez **sur Exécuter à nouveau.**
    
&nbsp;&nbsp;&nbsp;b. Dans la page **Tâches de certificats disponibles,** cliquez **sur Affecter un certificat existant.**
    
&nbsp;&nbsp;&nbsp;c. Dans la page **Affectation de** certificat, **sélectionnez Edge Interne** dans la liste.
    
&nbsp;&nbsp;&nbsp;d. Dans la page **Magasin de** certificats, sélectionnez le certificat que vous avez importé pour le edge interne (à partir de la section précédente).
    
&nbsp;&nbsp;&nbsp;e. Dans la page **Résumé de l’affectation** de certificat, consultez les paramètres, puis cliquez sur **Suivant** pour affecter le certificat.
    
&nbsp;&nbsp;&nbsp;f. Dans la page d’achèvement de l’Assistant, cliquez sur **Terminer.**
    
&nbsp;&nbsp;&nbsp;g. Une fois cette procédure terminée, il est vraiment bon d’ouvrir le logiciel en snap-in MMC Certificats sur chaque serveur Edge, de développer **certificats (ordinateur local),** de développer **Personnel,** de cliquer sur **Certificats** et de confirmer que le certificat Edge interne est répertorié dans le volet d’informations.
    
### <a name="external-edge-interface-certificates"></a>Certificats d’interface Edge externe

 
### <a name="1-create-the-certificate-request"></a>1. Créer la demande de certificat

&nbsp;&nbsp;&nbsp;a. Connectez-vous à l’un de vos serveurs Edge, démarrez l’Assistant Déploiement, puis à l’étape 3 : Demander, installer ou attribuer des **certificats,** cliquez sur Exécuter (ou exécuter à **nouveau,** si vous avez déjà exécuté cet Assistant).
    
&nbsp;&nbsp;&nbsp;b. Dans la page **Tâches se rapportant aux certificats disponibles**, cliquez sur **Créer une demande de certificat**.
    
&nbsp;&nbsp;&nbsp;c. Dans la page **Demande de** certificat, assurez-vous que le certificat **Edge** externe est sélectionné, puis cliquez sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;d. Dans la page Demandes différées ou **immédiates,** cliquez sur Préparer la demande **maintenant, mais envoyez-la ultérieurement.**
    
&nbsp;&nbsp;&nbsp;e. Dans **la** page Fichier de demande de certificat, entrez la partie complète et le nom de fichier pour l’endroit où le fichier sera enregistré (par exemple, c:\SkypeInternalEdgeCert.cer). Cliquez sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;f. Dans **la** page Spécifier un autre modèle de certificat, pour utiliser  un autre modèle que le modèle WebServer par défaut, cochez la case Utiliser un autre modèle de certificat pour la case à cocher Autorité de certification sélectionnée.
    
&nbsp;&nbsp;&nbsp;g. Dans la page Nom et paramètres de sécurité, procédez comme suit :
    
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   i. Dans **le nom convivial,** entrez un nom complet pour le certificat (par exemple, Edge externe).
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  ii. En **longueur de bit,** choisissez votre longueur de bit (la valeur par défaut est 2048, vous pouvez aller plus haut et être plus sécurisé, mais cela ralentit les performances).
    
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  iii. Si vous avez besoin d’un certificat exportable, vous devez cocher la case à cocher Marquer la clé privée du certificat comme **exportable.**
    
  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; iv. Cliquez sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;h. Dans la page **Informations sur l’organisation,** entrez le nom de votre organisation et de votre unité d’organisation. Vous pouvez entrer votre service ou service (informatique, par exemple).
    
&nbsp;&nbsp;&nbsp;i. Dans la page **Informations géographiques,** entrez vos informations d’emplacement.
    
&nbsp;&nbsp;&nbsp;j. Dans la page **Nom du sujet/Autres noms du** sujet, les informations nécessaires doivent être remplies automatiquement par l’Assistant.
    
&nbsp;&nbsp;&nbsp;k. Dans la page **Paramètre de domaine SIP** sur les autres noms du sujet, cochez la case du domaine pour ajouter un sip.\<sipdomain> à la liste des autres noms du sujet.
    
&nbsp;&nbsp;&nbsp;l. Dans la page **Configurer d’autres noms** du sujet supplémentaires, vous devez ajouter d’autres noms de sujet supplémentaires dont vous avez besoin.
    
&nbsp;&nbsp;&nbsp;m. Dans la page **Résumé de la** demande, regardez les informations de certificat qui seront utilisées pour générer votre demande. Si vous devez apporter des modifications, revenir en arrière et le faire maintenant.
    
&nbsp;&nbsp;&nbsp;n. Lorsque vous êtes prêt, cliquez sur Suivant pour générer le fichier CSR que  vous devrez fournir à l’ac (vous pouvez également cliquer sur Afficher le journal pour consulter le journal de la demande de certificat). 
    
&nbsp;&nbsp;&nbsp;o. Une fois la demande générée, vous pouvez cliquer sur  **Afficher** pour examiner le certificat et terminer pour fermer la fenêtre. Le contenu du fichier CSR doit être attribué à votre ca, afin qu’il puisse générer un certificat que vous pouvez importer sur cet ordinateur dans la section suivante.
    
&nbsp;&nbsp;&nbsp;p. (FACULTATIF) Vous pouvez, lors de l’envoi du contenu de la CSR, être invité à fournir certaines informations, comme suit (les CA varient considérablement, ce qui n’est peut-être pas obligatoire) :
    
  - **Microsoft** en tant que plateforme serveur
    
  - **IIS comme** version
    
  - **Serveur Web comme** type d’utilisation
    
  - **PKCS7 comme** format de réponse
    
 
### <a name="2-import-the-certificate"></a>2. Importer le certificat

&nbsp;&nbsp;&nbsp;a. Log on, as a member of the local Administrators group, to the Edge Server you made your certificate request from in the last procedure.
    
&nbsp;&nbsp;&nbsp;b. Dans l’Assistant Déploiement, à côté de **l’étape 3. Demander, installer ou attribuer des certificats,** cliquez **sur Exécuter à nouveau.**
    
&nbsp;&nbsp;&nbsp;c. Dans la page **Tâches de certificats disponibles,** cliquez sur **Importer un certificat à partir d’un . Fichier P7b, .pfx ou .cer**.
    
&nbsp;&nbsp;&nbsp;d. Dans la page **Importer** un certificat, tapez le chemin d’accès complet et  le nom de fichier du certificat que vous avez obtenu dans la section précédente (ou vous pouvez cliquer sur Parcourir pour rechercher et choisir le fichier de cette façon). Si votre certificat contient une clé privée, veillez à sélectionner Le fichier de certificat contient la clé privée du certificat **et** entrez le mot de passe de la clé privée. Cliquez **sur Suivant** lorsque vous êtes prêt.
    
&nbsp;&nbsp;&nbsp;e. Dans la page **Résumé de l’importation de** certificat, consultez les informations récapitulatifs, puis cliquez sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;f. Dans la page **Exécution de commandes,** vous pouvez passer en revue le résultat de l’importation une fois l’importation terminée en cliquant sur **Afficher le journal.** Cliquez **sur Terminer** pour terminer l’importation du certificat.
    
&nbsp;&nbsp;&nbsp;g. Si vous avez d’autres serveurs Edge dans un pool, vous devez également suivre les deux procédures suivantes. S’il s’agit d’un serveur Edge autonome, vous avez terminé avec les certificats externes.
    
 
### <a name="3-export-the-certificate"></a>3. Exporter le certificat

&nbsp;&nbsp;&nbsp;a. Assurez-vous que vous êtes connecté au serveur Edge sur qui vous avez importé le certificat en tant qu’administrateur local.
    
&nbsp;&nbsp;&nbsp;b. Cliquez **sur Démarrer,** **Exécuter** (ou **ouvrir la** recherche), puis **tapez MMC**.
    
&nbsp;&nbsp;&nbsp;c. Dans la console MMC, cliquez sur **Fichier,** puis sur **Ajouter/Supprimer un logiciel en snap-in**.
    
&nbsp;&nbsp;&nbsp;d. Dans la **zone Ajouter ou supprimer des logiciels** en un clin d’œil, cliquez sur **Certificats,** puis cliquez sur **Ajouter**.
    
&nbsp;&nbsp;&nbsp;e. Dans la **boîte de dialogue Certificats** en ligne, sélectionnez **Compte d’ordinateur.** Cliquez sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;f. Dans la **boîte de dialogue** Sélectionner un ordinateur, **sélectionnez Ordinateur local : (l’ordinateur sur qui cette console s’exécute).** Cliquez sur **Terminer**. Cliquez **sur OK** et la configuration de la console MMC est terminée.
    
&nbsp;&nbsp;&nbsp;g. Double-cliquez **sur Certificats (ordinateur local)** pour développer les magasins de certificats. **Double-cliquez sur Personnel,** puis cliquez **sur Certificats.**
    
   > [!NOTE]
   > Vous êtes peut-être là et vous ne voyez aucun certificat dans le magasin personnel de certificats pour l’ordinateur local. Vous n’avez pas besoin de vous déplacer, si la clé n’est pas là, aucune clé privée n’est associée au certificat importé. Essayez les étapes de demande et d’importation ci-dessus une fois de plus, et si vous êtes sûr d’avoir tout ce qu’il faut, demandez à votre administrateur d’ac ou fournisseur. 
  
&nbsp;&nbsp;&nbsp;h. Dans le **magasin personnel de certificats** de l’ordinateur local, cliquez avec le bouton droit sur le certificat que vous exportez. **Sélectionnez toutes les** tâches dans le menu résultant, puis cliquez sur **Exporter.**
    
&nbsp;&nbsp;&nbsp;i. Dans l’**Assistant Exportation de certificat**, cliquez sur **Suivant**. Sélectionnez **Oui, exporter la clé privée.** Cliquez sur **Suivant**.
    
   > [!NOTE]
   > Si **oui, l’exportation de** la clé privée n’est pas disponible, alors la clé privée de ce certificat n’a pas été marquée pour exportation avant que vous ne l’avez obtenu. Vous devez demander à nouveau le certificat au fournisseur, avec la clé privée définie pour l’exportation, avant de réussir cette étape.
  
&nbsp;&nbsp;&nbsp;j. Dans la boîte de dialogue Exporter les formats de fichiers, sélectionnez Informations Exchange - PKCS#12 (. PFX), puis sélectionnez ce qui suit :
    
 &nbsp;&nbsp;&nbsp;  i. Incluez tous les certificats dans le chemin d’accès de certification, si possible.
    
 &nbsp;&nbsp;&nbsp;  ii. Exporter toutes les propriétés étendues.
    
   > [!NOTE]
   > **NE** **SÉLECTIONNEZ JAMAIS Supprimer la clé privée si l’exportation a réussi.** Cela signifie que vous devez réimporter le certificat et la clé privée vers ce serveur Edge.
  
&nbsp;&nbsp;&nbsp;k. Si vous souhaitez attribuer un mot de passe pour protéger la clé privée, vous pouvez taper un mot de passe pour la clé privée. Reentez le mot de passe pour confirmer, puis cliquez sur **Suivant**.
    
&nbsp;&nbsp;&nbsp;l. Tapez un chemin d’accès et un nom de fichier pour le certificat exporté, à l’aide de l’extension **de fichier .pfx**. Le chemin d’accès doit être accessible par les autres serveurs Edge du pool, ou vous devez déplacer le fichier au moyen d’un support externe (par exemple, un lecteur USB). Cliquez **sur Suivant** lorsque vous avez fait votre choix.
    
&nbsp;&nbsp;&nbsp;m. Consultez le résumé de la boîte de dialogue **Fin de** l’Assistant Exportation de certificat, puis cliquez sur **Terminer.**
    
&nbsp;&nbsp;&nbsp;n. Cliquez **sur OK** dans la boîte de dialogue d’exportation réussie.
    
&nbsp;&nbsp;&nbsp;o. Vous devez maintenant revenir à la section Importer le certificat avant cela et importer le certificat sur tous vos serveurs Edge restants, puis procéder à l’affectation, ci-dessous.
    
 
### <a name="4-assign-the-certificate"></a>4. Affecter le certificat

&nbsp;&nbsp;&nbsp;a. Sur **chaque** serveur Edge, dans l’Assistant Déploiement, à côté de **l’étape 3. Demander, installer ou attribuer des certificats,** cliquez **sur Exécuter à nouveau.**
    
&nbsp;&nbsp;&nbsp;b. Dans la page **Tâches de certificats disponibles,** cliquez **sur Affecter un certificat existant.**
    
&nbsp;&nbsp;&nbsp;c. Dans la page **Affectation de** certificat, **sélectionnez Edge Externe** dans la liste.
    
&nbsp;&nbsp;&nbsp;d. Dans la page **Magasin de** certificats, sélectionnez le certificat que vous avez importé pour le edge externe (dans la section précédente).
    
&nbsp;&nbsp;&nbsp;e. Dans la page **Résumé de l’affectation** de certificat, consultez les paramètres, puis cliquez sur **Suivant** pour affecter le certificat.
    
&nbsp;&nbsp;&nbsp;f. Dans la page d’achèvement de l’Assistant, cliquez sur **Terminer.**
    
&nbsp;&nbsp;&nbsp;g. Une fois cette procédure terminée, il est vraiment bon d’ouvrir le logiciel en snap-in MMC Certificats sur chaque serveur, de développer **certificats (ordinateur local),** de développer **Personnel,** de cliquer sur **Certificats** et de confirmer que le certificat Edge interne est répertorié dans le volet d’informations.
    
   > [!NOTE]
   > Vous aurez également besoin de configurer les certificats pour votre serveur proxy inverse. 
  
## <a name="starting-the-edge-servers"></a>Démarrage des serveurs Edge

Une fois l’installation terminée, vous devez démarrer les services sur chaque serveur Edge de votre déploiement :
  
1. Sur chaque serveur Edge, dans l’Assistant **Déploiement,** à côté de l’étape **4 : Démarrer** les services, cliquez sur **Exécuter**.
    
2. Dans la page **Démarrer Skype Entreprise Server Services,** consultez la liste des services, puis cliquez sur **Suivant** pour démarrer les services.
    
3. Une fois les services démarrés, vous pouvez cliquer sur **Terminer** pour fermer l’Assistant.
    
4. (Facultatif) Toujours sous **l’étape 4 : Démarrer les services,** cliquez sur **État des services.**
    
5.  Dans la **MMC Services** sur chaque serveur, vérifiez que tous les services Skype Entreprise Server sont en cours d’exécution.
    

