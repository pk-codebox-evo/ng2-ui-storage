# ng2-ui-storage
Provides memory storage fallback for localStorage and sessionStorage

## Usage

Setup Preference. The default preference is 'sessionStorage'.

    import { Ng2Storage } from "./ng2-storage";
    
    @Component({
      selector: 'my-app',
      templateUrl: './app.html',
      providers: [Ng2Storage]
    })
    export class AppComponent {
    
      constructor(private storage: Ng2Storage) {
        storage.preference = 'localStorage';
      }
    }

Use it in your service or component

    import { Ng2Storage } from "./ng2-storage";
    export class MyService {
      constructor(private storage: Ng2Storage) {}
      myFunc() {
        this.storage.setItem('foo', 1);
        this.storage.getItem('foo');
        this.storage.removeItem('foo');
        this.storage.clear();
      }
    }
