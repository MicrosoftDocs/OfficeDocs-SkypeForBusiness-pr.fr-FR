
Pour aider vos utilisateurs à planifier plus facilement des réunions dans une salle Teams, vous pouvez créer des listes de salles et des emplacements dans Exchange Online. 

Les listes de salles Exchange et les emplacements Outlook sont utilisés pour contrôler les comptes de ressources (et par conséquent les salles Teams auxquels ils sont associés) s’affichent dans le Finder de salle d’Outlook. Room Finder est une fonctionnalité d’Outlook qui permet aux utilisateurs de trouver des salles proches d’eux, disponibles pour la réservation et répondant à d’autres critères tels que la disponibilité d’un affichage.

Les listes de salles sont un type spécial de groupe de distribution Exchange qui vous permet de regrouper les comptes de ressources (et par conséquent les salles Teams auxquels ils sont associés) de manière significative. Par exemple, vous souhaiterez peut-être créer des listes de salles pour toutes les salles de chaque bâtiment de votre campus.

Outlook Places vous permet de définir des attributs spécifiques sur un compte de ressource et sa salle Teams. Voici quelques-uns des attributs que vous pouvez définir :

- Bâtiment
- Ville
- Capacité
- Indique si l’emplacement est accessible en fauteuil roulant
- Noms audio, vidéo et d’affichage

À l’aide d’une combinaison de listes de salles et d’attributs de place sélectionnés par un utilisateur, Room Finder dans Outlook affiche la liste des salles disponibles pour réservation. Pour tirer le meilleur profit des listes de salles et des lieux, créez des listes de salles en fonction d’un attribut de lieu, tel que la construction. Par exemple, définissez les attributs de ville et de lieu de construction pour chaque compte de ressource, puis ajoutez chaque compte de ressource à une liste de salles de construction. Lorsqu’un utilisateur tente de choisir une salle à réserver, Outlook affiche une liste de villes et les listes de salles disponibles dans chacune de ces villes.

> [!IMPORTANT]
> Chaque compte de ressource doit avoir ses attributs de place définis. Si ces attributs, en particulier la ville, la construction et la capacité, ne sont pas définis, ces salles ne s’affichent pas comme options disponibles pour la réservation, même si une liste de salles les contient.

Pour créer une liste de salles, suivez les instructions fournies dans [Créer une liste de salles](/exchange/recipients/room-mailboxes?view=exchserver-2019&preserve-view=true#create-a-room-list).

Pour configurer les attributs d’emplacement d’un compte de ressource, consultez [Set-Place](/powershell/module/exchange/set-place).
